---
title: Development of the Target Scoring System
date: 2022-06-20 19:00:00 +0800
categories: [Project]
tags: [project, c++]
---

# Stage 1: Target Board Image Retrieval

Firstly, the image taken from the camera needed to be cropped and aligned. The program implemented two methods to achieve this. 

![input image](/assets/img/resources/20220620_imgs/shot_1.JPG){: width="400" }
_Image taken from the camera_

## Method 1: ORB Matching

The first of which uses the ORB(Oriented FAST and Rotated BRIEF) to match the features between the image taken by the camera and the model image. 

![reference target board](/assets/img/resources/20220620_imgs/aligned_shot_0.JPG){: width="300" }
_Reference Target Image_

Then, a ratio test is performed to obtain only the good matches. 

| Matches                                                                       | Good Matches                                                                            |
| :---------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------- |
| `matches.size() = 200`                                                        | `good_matches.size() = 35`                                                              |
| ![matches](/assets/img/resources/20220620_imgs/match_img.png){: width="300" } | ![good matches](/assets/img/resources/20220620_imgs/good_match_img.png){: width="300" } |

![output image](/assets/img/resources/20220620_imgs/warped_img.png){: width="400" }
_Output Image_


## Method 2: Shape Detection

![shape detection](/assets/img/resources/20220620_imgs/outline.png){: width="500" }
_Output Image_

![outline selected](/assets/img/resources/20220620_imgs/outline_selected.png){: width="500" }
_Output Image_

![input image](/assets/img/resources/20220620_imgs/outline_selected_input_img.png){: width="500" }
_Output Image_

未完待续


# Stage 2: Computing the Shooting Score

![target outline](/assets/img/resources/20220620_imgs/target_circle.png){: width="400" }
_Target Outline_

![shot contour](/assets/img/resources/20220620_imgs/shot_contour.png){: width="400" }
_Shot contour_

![shot location](/assets/img/resources/20220620_imgs/shot_location.png){: width="400" }
_Shot Location_

![result](/assets/img/resources/20220620_imgs/output.png){: width="400" }
_Result Drawn_