# Hair_matting

## Intoduction
Welcome to our Hair Matting project repository. Here, we aim to simplify the process of extracting high-quality hair mattes from images using a streamlined workflow. Starting with hair segmentation using the `bisenet` model, we guide you through creating accurate trimaps and ultimately achieving detailed hair matting with the FBA_Matting model. This README provides all the necessary steps and resources, including how to prepare your images for testing and utilize the `main.ipynb` notebook for processing. Our method ensures precise and visually appealing results, enhancing the quality of your hair editing projects.


## Reference
- bisenet
- [FBA_Matting](https://github.com/MarcoForte/FBA_Matting)

## Hair Segmentation
To kick off the process of generating a high-quality hair matte, we utilize the `bisenet` pre-trained model. This model is instrumental in creating a coarse hair binary mask, distinguishing hair from the rest of the image. The use of `bisenet` is chosen for its proven efficiency and accuracy in segmenting hair, laying the groundwork for the detailed matting process that follows.

This initial segmentation step is crucial, as it defines the areas of focus for refining the hair matte. It ensures that our subsequent processing is targeted and effective, leading to a more refined and realistic hair matte outcome. This method sets the stage for the advanced steps in our workflow, aiming to deliver high-quality results that are both precise and visually appealing.

## Hair Trimap
The mask is then dilated and eroded to accurately distinguish between hair, background, and uncertain areas within the image. Each region is marked with specific values in the trimap (255 for hair, 0 for background, and 128 for uncertain areas), playing a crucial role in the hair matting process. The final trimap is saved to a specified path. Through this process, foundational work for achieving high-quality hair matting results is conducted.

## Hair Matting
To obtain a high-quality hair matte, you can utilize the FBA_Matting model alongside the original image and the generated trimap. This process involves estimating the matte by leveraging the capabilities of the fba_matting model, which has been specifically designed to handle intricate details and provide precise hair matting results. To achieve this, you can use the pre-trained matting model named [FBA.pth](https://drive.google.com/uc?id=1T_oiKDE_biWf2kqexMEN7ObWqtXAzbB1). This model has been trained on a diverse set of images and trimaps, ensuring that it can accurately extract hair mattes across a wide range of scenarios. By following this approach, you can enhance your hair editing projects with detailed and realistic hair mattes, significantly improving the overall visual quality of your work.


## Test 
To prepare for testing, please place your images in the `dataset/img/test` folder. These images can then be tested using the `main.ipynb` notebook. This setup allows for a streamlined process to evaluate the performance of the model with your specific images, ensuring you can directly observe and assess the outcomes of the processing steps outlined in our workflow.