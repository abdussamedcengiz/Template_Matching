import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import org.opencv.core.Core;
import org.opencv.core.Mat;
import org.opencv.core.MatOfFloat;
import org.opencv.core.MatOfRect;
import org.opencv.core.Rect;
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.imgproc.Imgproc;

public class Program {
    public static void main(String[] args) {
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);

        String[] imageFiles = new File("C:\\Users\\SAMET\\Downloads\\drive-download-20230525T092359Z-001.zip").list();
        List<Mat> images = new ArrayList<>();
        Map<Integer, Mat> processedImages = new HashMap<>();

        for (int i = 0; i < imageFiles.length; i++) {
            images.add(Imgcodecs.imread(imageFiles[i]));

            Mat grayImage = new Mat();
            Imgproc.cvtColor(images.get(i), grayImage, Imgproc.COLOR_BGR2GRAY);
            grayImage.convertTo(grayImage, CvType.CV_32F);
            Mat processedImage = grayImage.clone();
            processedImages.put(i, processedImage);
        }

        List<Tuple<String, String, Double>> similarityList = findMostSimilarImages(images, processedImages);

        for (Tuple<String, String, Double> similarity : similarityList) {
            System.out.println("Image 1: " + similarity.getFirst());
            System.out.println("Image 2: " + similarity.getSecond());
            System.out.println("Similarity: " + similarity.getThird());
            System.out.println();
        }
    }

    static List<Tuple<String, String, Double>> findMostSimilarImages(List<Mat> images, Map<Integer, Mat> processedImages) {
        List<Tuple<String, String, Double>> similarityList = new ArrayList<>();

        for (int i = 0; i < images.size(); i++) {
            for (int j = i + 1; j < images.size(); j++) {
                double similarity = calculateSimilarity(processedImages.get(i), processedImages.get(j));
                similarityList.add(new Tuple<>(String.valueOf(i), String.valueOf(j), similarity));
            }
        }

        similarityList.sort((x, y) -> Double.compare(y.getThird(), x.getThird()));

        return similarityList;
    }

    static double calculateSimilarity(Mat processedImage1, Mat processedImage2) {
        Mat result = new Mat();
        Core.minMaxLoc(processedImage1, new MatOfFloat(), new MatOfFloat(), new MatOfRect(), new MatOfRect());
        double[] maxValues1 = result.get(0, 0);
        Core.minMaxLoc(processedImage2, new MatOfFloat(), new MatOfFloat(), new MatOfRect(), new MatOfRect());
        double[] maxValues2 = result.get(0, 0);

        return Math.max(maxValues1[0], maxValues2[0]);
    }
}

class Tuple<A, B, C> {
    private final A first;
    private final B second;
    private final C third;

    public Tuple(A first, B second, C third) {
        this.first = first;
        this.second = second;
        this.third = third;
    }

    public A getFirst() {
        return first;
    }

    public B getSecond() {
        return second;
    }

    public C getThird() {
        return third;
    }
}
