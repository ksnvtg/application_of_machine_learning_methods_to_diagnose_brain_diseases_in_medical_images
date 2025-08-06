After that, the entire dataset of patients was split into three subsets:
* 258 patients (69.9%) - training set (train.txt)
* 55 patients (14.9%) - validation set (val.txt)
* 56 patients (15.2%) - test set (test.txt)
Patients were randomly shuffled using a fixed random seed to ensure reproducibility. The split results were saved into text files for automatic loading during training, as illustrated in Fig 1.
<img width="858" height="518" alt="зображення" src="https://github.com/user-attachments/assets/c081ec6d-6a62-41be-b8b0-19c06b2e4056" />
          Figure 1 - Divison of the dataset into Train (69.9%), Validation (14.9%), and Test (15.2%) subsets

<img width="442" height="282" alt="зображення" src="https://github.com/user-attachments/assets/690bfd23-bc8e-42a2-9a7d-861605f4a798" />
         Figure 2 - Results test model


**Evaluation Results on Test Dataset**
The model achieved high segmentation accuracy on the test dataset, especially for larger anatomical structures. The best performance was observed for the **background** class with a Dice score of **99.69%**, followed by the **enhancing tumor** with **79.91%**, and **edema** with **73.32%**. The **necrosis** class showed the lowest performance with a Dice score of **57.85%** and Recall of **49.66%**, which can be attributed to its small spatial area and visual complexity.
These results indicate that the model is well-suited for segmenting large and well-defined regions. However, performance on small or visually ambiguous regions remains challenging. To address this, incorporating class weights in the loss function is recommended, giving more importance to underrepresented or difficult classes.
