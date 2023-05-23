Here is a list of image deblurring and sharpening-related methods provided by the OpenCV library in C++, along with detailed explanations and examples for each method:

1. Image Deblurring:

- `cv::deblur`: Deblurs an image using a specific algorithm.
  Explanation: This function deblurs an image using a specific algorithm specified by the user.

  Example:
  ```cpp
  cv::Mat blurredImage = cv::imread("blurred.jpg");
  cv::Mat deblurredImage;
  cv::deblur(blurredImage, deblurredImage, cv::Size(5, 5));
  cv::imshow("Deblurred Image", deblurredImage);
  cv::waitKey(0);
  ```

- `cv::deconvolve`: Deconvolves an image using a specific algorithm.
  Explanation: This function performs image deconvolution, which aims to recover the original image from a blurred or degraded version using a specific deconvolution algorithm.

  Example:
  ```cpp
  cv::Mat blurredImage = cv::imread("blurred.jpg");
  cv::Mat kernel = (cv::Mat_<float>(3, 3) << 0, -1, 0, -1, 5, -1, 0, -1, 0);
  cv::Mat deconvolvedImage;
  cv::deconvolve(blurredImage, kernel, deconvolvedImage);
  cv::imshow("Deconvolved Image", deconvolvedImage);
  cv::waitKey(0);
  ```

2. Image Sharpening:

- `cv::filter2D`: Applies a sharpening filter to an image.
  Explanation: This function applies a sharpening filter to an image, enhancing the edges and details.

  Example:
  ```cpp
  cv::Mat image = cv::imread("input.jpg");
  cv::Mat kernel = (cv::Mat_<float>(3, 3) << 0, -1, 0, -1, 5, -1, 0, -1, 0);
  cv::Mat sharpenedImage;
  cv::filter2D(image, sharpenedImage, -1, kernel);
  cv::imshow("Sharpened Image", sharpenedImage);
  cv::waitKey(0);
  ```

- `cv::detailEnhance`: Enhances the details in an image.
  Explanation: This function enhances the details in an image, making them more prominent and visually pleasing.

  Example:
  ```cpp
  cv::Mat image = cv::imread("input.jpg");
  cv::Mat enhancedImage;
  cv::detailEnhance(image, enhancedImage);
  cv::imshow("Enhanced Image", enhancedImage);
  cv::waitKey(0);
  ```

- `cv::unsharpMask`: Applies an unsharp mask to an image.
  Explanation: This function applies an unsharp mask to an image, sharpening it by enhancing the edges and details.

  Example:
  ```cpp
  cv::Mat image = cv::imread("input.jpg");
  cv::Mat unsharpMaskedImage;
  cv::unsharpMask(image, unsharpMaskedImage, 5, 1.5);
  cv::imshow("Unsharp Masked Image", unsharpMaskedImage);
  cv::waitKey(0);
  ```

These are some of the image deblurring and sharpening-related methods provided by the OpenCV library in C++. Each method serves a specific purpose in restoring image sharpness and reducing blurriness. The examples demonstrate how to use them in practice. Remember to adapt the code and parameters based on your specific requirements and image data.