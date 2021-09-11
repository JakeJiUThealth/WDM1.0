A Novel Computational Framework for Precision Diagnosis and Subtype Discovery of Plant with Lesion

Abstract

Integration of high-throughput phenotypic image data and computer vision technology provides an effective strategy for plant disease diagnosis in real time.We proposed a novel computational framework for plant disease identification and subtype discovery through an image clustering strategy.

Data

    Description

Data 		Description
lentil 		11 levels from 0-5
cherry 		healthy & powdery mildew
strawberry 	healthy & leaf scorch
tomato 		bacterial spot & leaf mold & yellow leaf curl virus


    Plant disease image data are available at the following link：https://xf-data-bucket.oss-cn-hangzhou.aliyuncs.com/data.rar

Environment and Tools

Keras 2.2 & Tensorflow 1.13.1 GPU
numpy 1.14.0
opencv-python 4.2.0.34
pandas 0.25.3
scikit-learn 0.22.2

IDE Used

jupyter notebook

Code

1.
    Image Preprocessing
    Image preprocessing includes background separation, image panning, image flipping, image rotation and target area segmentation.Take the code for splitting the target area as an example. Create the original image path and the target path, in this case ‘input/’ and ‘output/’.

source_path = "input/"  
save_path = "output/"  

if not os.path.exists(save_path):
 	os.mkdir(save_path)

file_names = os.listdir(source_path)

for i in range(len(file_names)):
	x = cropping_img(source_path + file_names[i])  
	cv2.imwrite(save_path + file_names[i], x)
2.
    Feature extraction
    The feature extraction section contains network construction and dimensionality reduction. Plant disease images of different sizes are allowed as input and the output is low-dimensional data.
3.
    Visualization
    The visualisation section shows the clustering results for the diagnosis of plant disease species and the classification of disease levels.


