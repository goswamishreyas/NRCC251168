☁️ Automatic Cloud and Shadow Masking from Resourcesat-2/2A LISS-4 Satellite Images
🔬 Offline EO Data Processing Challenge — NRSC Hackathon Submission
📌 Project Overview
This project presents a machine learning pipeline for automatic cloud and cloud-shadow masking from Resourcesat-2/2A LISS-4 Level-2 satellite images. The goal is to accurately identify and mask out three classes — Clouds, Shadows, and No-Cloud regions — using pixel-wise classification techniques.

The solution was developed as part of the NRSC Hackathon Offline EO Data Processing Challenge using open-source tools and efficient neural network models.

🎯 Objectives
Develop a lightweight yet effective pixel-wise classifier to detect Clouds, Shadows, and No-Cloud areas from LISS-4 imagery.

🗂️ Dataset Summary
Satellite: Resourcesat-2/2A LISS-4 (Level 2 Products)

20 images used for training and validation (80/20 split)

13 independent, unseen images used for testing

Class Distribution:

Class	Train Samples	Validation Samples	Test Samples
No Cloud (0)	8930	2233	5273
Cloud (1)	8302	2075	5567
Shadow (2)	9725	2432	4728

Preprocessing involved converting DN values to TOA reflectance using standard physical formulas and metadata.

🧠 Model & Methodology
A Multi-Layer Perceptron (MLP) classifier was adopted for its:

✅ Ability to handle non-linear class boundaries
✅ Efficiency with pixel-wise datasets
✅ Faster training compared to CNNs, while maintaining competitive accuracy

Architecture Highlights:

4 Fully Connected Layers with ReLU activation

Dropout regularization to prevent overfitting

Output layer predicts 3 classes: No Cloud, Cloud, Shadow

StandardScaler used for feature normalization

The model was trained using PyTorch with a class-weighted loss to address class imbalances.

📊 Results & Performance
Dataset	Overall Accuracy	F1-Score
Validation	87%	86%
Test (Unseen)	73.3%	73.6%

Class-wise Test Set Highlights:

Clouds: High precision (91%), moderate recall (73%)

Shadows: Good recall (80%), moderate precision (67%)

No Cloud: Lower precision and recall (~66%), with notable confusion against Shadows

⚡ Key Insights
The model effectively distinguishes Clouds but faces challenges between No Cloud and Shadow classes due to spectral overlaps.

Training and validation curves indicate stable training with no major overfitting.

Comparative testing shows the MLP outperforms a baseline Random Forest model.

🔧 Future Improvements
Incorporating spectral indices (e.g., band ratios)

Adding spatial features using texture or patch-based approaches

Integration of DEM and solar geometry for improved shadow detection

Expanding the training dataset with diverse seasonal samples

Potential use of CNNs for capturing spatial context in large-scale datasets


👨‍💻 Team Members
Shreyas Goswami (Bhoomicam Pvt. Ltd., TiDES, IIT Roorkee)

Ishfaqul Haque (IIT Roorkee)

Akash K (IIT Roorkee)

Akash Pandey (IIT Roorkee)

🚀 Acknowledgments
This project is developed as part of the NRSC Hackathon — Offline EO Data Processing Challenge using only open-source packages.
