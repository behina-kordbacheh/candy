# 🍬 Candy Popularity Prediction

A small machine learning project exploring what makes a candy popular. Using candy characteristics such as chocolate, fruit flavor, caramel, texture, and sugar content, I trained and compared two classification models: a **Decision Tree** and a **Random Forest**.

The project includes exploratory data analysis, visualizations, model evaluation, and a colorful interactive dashboard.

## 📊 Dataset

The project uses `candy-data.csv`, containing **85 candies** and their characteristics. The `winpercent` column represents each candy's win percentage in head-to-head comparisons.

Some of the features used for prediction include:

- Chocolate, fruity, caramel, nougat, and peanut/almond ingredients
- Crispy rice/wafer, hard candy, candy bar, and pluribus indicators
- Sugar percentage (`sugarpercent`) and price percentile (`pricepercent`)

To turn this into a classification problem, I created a new column called **`popular`**:

- `1` — the candy's `winpercent` is **above** the dataset median
- `0` — the candy's `winpercent` is **at or below** the median

This is a relative popularity label defined for this project, not a label supplied with the original dataset.

## 🧠 What I Did

1. Loaded the dataset and checked its columns and data types.
2. Visualized the distribution of win percentages and compared chocolate and fruity candies.
3. Created the binary popularity target using the median win percentage.
4. Split the data into training (80%) and testing (20%) sets, using stratification.
5. Trained a **Decision Tree Classifier** (`max_depth=4`, `min_samples_leaf=2`).
6. Evaluated the tree with test accuracy, a confusion matrix, and 10-fold cross-validation.
7. Trained a **Random Forest Classifier** (`max_depth=6`, `min_samples_leaf=2`).
8. Compared test accuracy, confusion matrices, and feature importances.

## 📈 Results

The saved notebook outputs show:

| Model | Test accuracy |
| --- | ---: |
| Decision Tree | 82.35% |
| Random Forest | 82.35% |

Both models achieved the same test accuracy in this notebook run. Since the dataset is small and the notebook does not fix a random seed, results may differ when you rerun it. Accuracy alone is not enough to establish how well these models would generalize to new candies.

## 🛠️ Tools & Libraries

- Python
- pandas
- matplotlib
- seaborn
- scikit-learn
- Jupyter Notebook

## 🚀 How to Run

1. Clone or download this repository.
2. Install the required Python packages:

   ```bash
   pip install pandas matplotlib seaborn scikit-learn notebook
   ```

3. Keep `candy-data.csv` in the same folder as the notebook.
4. Start Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open `candy_project_github.ipynb` and run the cells in order.

## 🎨 Interactive Dashboard

I also created **CandyLab**, a colorful HTML dashboard to explore the candy dataset and model predictions.

If `CandyLab.html` is included in the repository, open it in your browser to explore the interactive interface. No separate web server is required.

## 📁 Project Files

```text
├── README.md
├── candy_project_github.ipynb   # Data analysis and machine learning
├── candy-data.csv               # Candy dataset
└── CandyLab.html                # Optional interactive dashboard
```

## 💡 What I Learned

This project was a chance to practice the full workflow of a simple classification task: exploring data, creating a target variable, training models, and checking their performance. It also helped me see why visualizations and feature importance can be useful alongside accuracy scores.

---

*Made as a hands-on Python and machine learning project.*
