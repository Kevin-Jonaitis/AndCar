#include <jni.h>
#include <opencv2/core/core.hpp>
#include <opencv2/imgproc/imgproc.hpp>
#include <opencv2/features2d/features2d.hpp>
#include <vector>

using namespace std;
using namespace cv;

extern "C" {
JNIEXPORT void JNICALL Java_org_opencv_samples_tutorial4_Sample4View_FindFeatures(JNIEnv* env, jobject thiz, jlong addrGray, jlong addrRgba)
{
    Mat* pMatGr=(Mat*)addrGray;
    Mat* pMatRgb=(Mat*)addrRgba;
    vector<KeyPoint> v;

    FastFeatureDetector detector(50);
    detector.detect(*pMatGr, v);
    for( size_t i = 0; i < v.size(); i++ )
        circle(*pMatRgb, Point(v[i].pt.x, v[i].pt.y), 10, Scalar(255,0,0,255));
}

}

	Imgproc.cvtColor(mRgba, mIntermediateMat, Imgproc.COLOR_RGB2HSV_FULL);
    	
    	Core.inRange(mIntermediateMat, lo, hi, mIntermediateMat2); // green
    	Imgproc.dilate(mIntermediateMat2, mIntermediateMat2, mEmpty);
    	//
    	List<MatOfPoint> contours = new ArrayList<MatOfPoint>();
    	Mat hierarchy = new Mat();
    	Imgproc.findContours(mIntermediateMat2, contours, hierarchy,Imgproc.RETR_LIST, Imgproc.CHAIN_APPROX_SIMPLE);
    	Log.d("processFrame", "contours.size()" + contours.size());
    	//gets the size of the image
    	screenX = mRgba.size().width;
    	screenY = mRgba.size().height;
    	currentMaxArea = 0;
    	int indexMaxArea = -1;
       for (int i = 0; i < contours.size(); i++) {
    	   double s = Imgproc.contourArea(contours.get(i));
             if(s > currentMaxArea){
    		    indexMaxArea = i;
    		    currentMaxArea = s;
    	     }
       } 