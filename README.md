# FocusGuard (Student Attention Monitoring System)


Hetik Chandaria, Atharva Chiplunkar, Tanmay Desai, Vatsal Mehta


## Abstract
Due to time and resource constraints, the COVID-19 epidemic increased demand for academic online courses, which in turn increased the need for efficient online exams. Consequently, conducting online exams effectively and reliably became one of the most important and difficult topics in higher education. Online lectures have experienced certain issues in the past. Online lectures have the drawback of making students more prone to distractions and, frequently, to leaving them feeling sleepy. Students are taking advantage of the fact that tests are being given online by not administering them fairly. As there is little chance of being discovered when taking examinations online, students frequently cheat. To ensure that students are delivering tests fairly, we therefore suggest a method that tracks a student's drowsiness during lectures and their eye movement during exams. The system tracks the mentioned metrics by using facial recognition, followed by a variety of algorithms and image processing approaches. HOG-based feature extraction is used for facial identification. The student is then informed, and the teacher is also provided a summary of the student's behavior throughout the lecture or exam at the same time. To prevent students from switching tabs during tests, we have also included the option for uploading the answer sheet along with the question paper on the same system. The system also detects if the student has changed tabs.

**Keywords:** HOG, dlib, face detection, Eye Aspect Ratio, Computer Vision.

## 1. INTRODUCTION
The Covid-19 pandemic was classified by the World Health Organization as a current hazard to humanity. With the help of this pandemic, many activities, including those related to education, were successfully shut down on a global scale. As a result, there was a significant crisis-response migration of institutions to online learning as the educational platform. Due to reduced teacher-student interaction and the potential for online learning to become repetitive, students may become sleepy and the problem of students not paying attention rises. The goal of this research is to create a system that can determine whether a student is awake and alert while taking online lectures.

### 1.1 DESCRIPTION
In this project, we created a method for determining whether or not the student is listening to the lecture. To determine whether the student is paying attention or not, we employed 2 different methods in this. First, we made sure the student wasn't feeling sleepy. Second, we made sure the pupil wasn't doing anything else but looking at the screen. In this, we checked the blinking rate and determined the eye aspect ratio.

### 1.2 PROBLEM FORMULATION
One of the main causes of lack of concentration in online classrooms is drowsiness. Since it interferes with the student's ability to concentrate, this condition could have terrible consequences. Therefore, one of the keys to avoid not paying attention in online classes is to recognize tiredness. In this study, we created an algorithm based on machine learning, pattern recognition, and computer vision that will employ all the pertinent features for a quick and precise classification of students' sleepiness.

### 1.3 SCOPE OF THE PROJECT
Multiple video chatting and meeting applications, including Google Meet, Zoom, MS Teams, etc., can be coupled with this project. It can be used to simultaneously identify these characteristics for each participant and provide the meeting's host with a summary. The system's precision can also be increased. It can also be integrated with the colleges' ERP systems to collect attendance automatically and save the data, which will free up teachers' time.

## 2. REVIEW OF LITERATURE
High eye blink rates signify a pupil who is feeling sleepy. Adults typically have a 2 to 10 second pause between each eye blink. The camera will capture the driver's eye after detecting the eye area, and it will count the number of blinks. The eye detection technology only picks up on eyes that are open, which will aid in identifying tiredness in drivers. By using this data, it is feasible to determine whether the driver has his or her eyes closed and to count the user's blinks. It is sufficient to monitor the blink rate of one eye out of two. The blink rate that lasts three to four seconds was thought to be a sign of weariness. The average blink interval for a healthy person is 2 to 10 seconds, and 10 blinks per minute are regarded as typical eye conditions. When a person's blink rate falls below 10 per minute, abnormal eye problems are thought to be present. These elements allow for the detection of tiredness when the eye is closed for an extended period of time.
EAR = ||(p2 − p6) -||(p3 − p5)/(2||p1 − p4||)
The Eye Aspect Ratio (EAR) between height and width of the eye is computed where p1 to p6 are the 2D landmark locations. The EAR is mostly constant when an eye is open and is getting close to zero while closing an eye. It is partially person and head pose insensitive.

### A. Overview Design
In order to fulfill these needs, the overall design concept of Student Attention detection is to take a picture with the camera and roughly estimate the condition of the students with data processing. To this end, the necessary hardware and software materials must be gathered. Arduino, a camera, and load cell sensors are all utilized for this project along with Python machine learning. OpenCV, HOG algorithms, and OPENCV packages are utilized for facial and eye detection.

### B. Face Detection
Student Attention Detection calls for hardware and software elements, including a camera to identify faces, eyes, and the rate at which they blink. Several techniques are used in this endeavor, and these are described in this paper.

### C. HOG Algorithm
In this project, the Histogram Oriented Gradient (HOG) algorithm is used to detect effective features for eye detection and extract HOG features from the image patterns and gives the precise region of eyes from the captured image of the student. This preprocessing of the image includes image resizing and color normalization.

### D. Eyes Detection
The next step is to evaluate a driver's level of tiredness based on how quickly their eyes are blinking after capturing the student's image and undergoing preprocessing. Every frame, values are calculated, and variations in blink rate are checked against the threshold value. HOG, which is helpful for face detection and gives an accurate eye detection rate, is used to successfully detect the rate at which eyes blink.

### E. Pre-trained Facial Landmark Detector
The pre-trained facial landmark detector in the Dlib package is used to find and locate facial landmarks. It comprises of two shape prediction models that locate 68 and 5 landmark points within a facial image, respectively, using data from the i-Bug 300-W dataset. 68 face landmarks have been employed in this method. In Dlib, a face detector that is based on histograms of oriented gradients (HOG) is employed. This technique creates histograms by using the frequency of an image's gradient direction in specific localized areas. As the false positive ratio is low, it frequently outperforms Haar cascades in terms of accuracy. Additionally, adjusting during testing requires fewer parameters. As it can describe contour and edge features incredibly well, it is highly ideal for face detection. Additionally, Dalal and Triggs [9] found that the HOG descriptor is effective in detecting humans in images, making it a good choice for drowsiness detection. 

## 2. PROPOSED SOLUTION
We used Python and OpenCV to build sleepiness detection for this method. The pre-trained facial landmark detector in the Dlib package is used to find and locate facial landmarks. It comprises of two shape prediction models that locate 68 and 5 landmark points within a facial image, respectively, using data from the i-Bug 300-W dataset. 68 face landmarks have been employed in this method. We employ the pose estimation issue to identify the student's head pose. In computer vision lingo, the pose estimation problem described is sometimes referred to as the Perspective-n-Point problem, or PNP. The objective of this challenge is to determine an item's posture given a calibrated camera and the locations of n 3D points on the object and the corresponding 2D projections in the image.

## 3 FLOW OF SYSTEM
![Flow diagram](images/image.jpg)
1. In this we first begin by identifying the face of the user from the video.
2. We then extract the coordinates of the eye from the face. 3. After getting the coordinates of the eye we then calculate the Eye Aspect Ratio.
4. We then calculate the blinking rate of the eyes.
5. If the blinking rate of the eyes is less than the threshold value it will alert the user.
6. If the blinking rate is above the threshold then we continue with monitoring the students.
7. We also check if the student is looking at the screen or not.
8. If the student is not looking at the screen then we will send an alert.

## 4.RESULTS AND DISCUSSION 
### 4.1 USER INTERFACE:
* Figure 2 - Home Page
![Flow diagram](images/image.jpg)
* Figure 3 - Online Lecture
![Flow diagram](images/image.jpg)
* Figure 4 - Drowsiness Detection in Lecture
![Flow diagram](images/image.jpg)
* Figure 5 - Online Exam
![Flow diagram](images/image.jpg)
* Figure 6 - File Upload
![Flow diagram](images/image.jpg)
* Figure 7 - Proctoring System
![Flow diagram](images/image.jpg)
* Figure 8 - Email notification for Malicious Activities
![Flow diagram](images/image.jpg)

## 5.TESTING:
Testing is the practise of assessing software to find discrepancies between input and desired results. Testing evaluates the product's quality. Software testing is a process of validation and verification. It is a procedure for testing fully integrated software. This test's objective is to assess how well the system complies with the given requirements. White box testing is frequently used for verification whereas black box testing is frequently utilised for validation. 1.Black-box testing-Black box testing is a testing method that ignores the internal workings of the system and concentrates on the results produced in response to any input and system execution. Additionally known as functional testing.
2. White-box Testing -White box testing is a testing method that considers a system's internal workings. Glass box testing and structural testing are other names for it.

### 5.1 TEST CASES:

## 6. RESULT AND DISCUSSION
The accuracy of the system was calculated by carrying out various tests under various lighting conditions and various facial conditions such as spectacles and and without spectacles. 
The accuracy for the two systems is as follows:
![Flow diagram](images/image.jpg)
Students had attended lectures and given exams under ideal lighting conditions so the overall accuracy comes down to :
![Flow diagram](images/image.jpg)

## 7. Experimental Setup

The 300-W is a face dataset made up of 300 photos taken inside and outdoors. It encompasses a wide range of identity, expression, lighting, stance, occlusion, and face size. A decent webcam and laptop or computer are also required.

## 8. Conclusion and Future Scope

Student attention detection fully complies with the system's goals and specifications. It assessed whether or not the learner was paying attention to the lecture using real-time video of the student. This made it easier for the teacher to keep an eye on whether or not the pupils in the online class were paying attention. Additionally, thanks to the proctoring system, professors can now tell whether a student is giving the exam honestly or engaging in any unethical behavior. Additional video chatting and meeting software, including Google Meet, Zoom, MS Teams, etc., can be coupled with this project. It can be used to simultaneously identify these characteristics for each participant and provide the meeting's host with a summary. The system's precision can also be increased. It can also be integrated with the colleges' ERP systems to collect attendance automatically and save the data, which will free up teachers' time.

## 9. References

1. Fouzia, R. Roopalakshmi, J. A. Rathod, A. S. Shetty and K. Supriya, "Driver Drowsiness Detection System Based on Visual Features," 2018 Second International Conference on Inventive Communication and Computational Technologies (ICICCT), 2018, pp. 1344-1347, doi: 10.1109/ICICCT.2018.8473203.
2. K. Satish, A. Lalitesh, K. Bhargavi, M. S. Prem and T. Anjali., "Driver Drowsiness Detection," 2020 International Conference on Communication and Signal Processing (ICCSP), 2020, pp. 0380-0384, doi: 10.1109/ICCSP48568.2020.9182237.
3. C. Yashwanth and J. S. Kirar, "Driver's Drowsiness Detection," TENCON 2019 - 2019 IEEE Region 10 Conference (TENCON), 2019, pp. 1622-1625, doi: 10.1109/TENCON.2019.8929429.
4. Tobias Brächter, Dietmar Gerhardt (2020); Camera Image Based Method of Real Time Gaze Detection and Interaction; International Journal of Scientific and Research Publications (IJSRP) 10(11) (ISSN: 2250-3153), DOI: [http://dx.doi.org/10.29322/IJSRP.10.11.2020.p10777](http://dx.doi.org/10.29322/IJSRP.10.11.2020.p10777)
