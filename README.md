# 📊 IPL Data Analysis Project

This project performs comprehensive exploratory data analysis (EDA) on IPL (Indian Premier League) match data. It uncovers insights about match outcomes, top-performing teams, players, venues, and more using Python data analysis and visualization libraries.

---

## 📁 Project Overview

The notebook analyzes **IPL.csv** using:

* **Pandas** – data loading & cleaning
* **NumPy** – numerical operations
* **Matplotlib & Seaborn** – data visualization

The objective is to answer common cricket analytics questions such as:

* Which team won the most matches?
* Which venue hosted the most matches?
* Who achieved the highest individual score?
* Which bowler had the best bowling figures?
* Who won by the biggest margin?

---

## 🔧 Technologies Used

| Library        | Purpose                             |
| -------------- | ----------------------------------- |
| **Pandas**     | Data loading, cleaning, analysis    |
| **NumPy**      | Numerical operations                |
| **Matplotlib** | Visual plots                        |
| **Seaborn**    | Enhanced statistical visualizations |

---

## 📂 Dataset Information

The project loads:

```python
df = pd.read_csv('IPL.csv')
```

Basic steps include:

* Checking dataset shape
* Handling missing values
* Exploring important match fields such as:

  * `match_winner`
  * `won_by`
  * `margin`
  * `venue`
  * `top_scorer`
  * `highscore`
  * `best_bowling`
  * `highest_wickets`

---

## 📌 Key Analysis & Insights

### **1️⃣ Team with Most Match Wins**

```python
match_wins = df['match_winner'].value_counts()
sns.barplot(y=match_wins.index, x=match_wins.values)
```

This visualization highlights which teams have dominated the league.

---

### **2️⃣ Most Played / Popular Venue**

```python
venue_count = df['venue'].value_counts().head(10)
sns.barplot(y = venue_count.index, x = venue_count.values)
```

Shows the top 10 venues with maximum matches hosted.

---

### **3️⃣ Highest Victory Margin (Runs)**

```python
df[df['won_by'] == 'Runs']
    .sort_values(by ='margin', ascending=False)
    .head(1)[['match_winner','margin']]
```

Identifies the team with the biggest win by runs.

---

### **4️⃣ Highest Individual Score**

```python
df[df['highscore'] == df['highscore'].max()]['top_scorer']
```

Finds the player with the maximum single-innings score.

---

### **5️⃣ Best Bowling Figures**

```python
df[df['highest_wickets'] == df['highest_wickets'].max()]
    [['best_bowling','best_bowling_figure']]
```

Highlights the bowler with the most impactful performance.

---

## 📸 Visualizations

The project includes multiple bar plots for easy comparison of:

* Match wins
* Venues
* Top performers

All visualizations are created using **Matplotlib** and **Seaborn**.

---

## 🚀 How to Run the Project

1. Install the dependencies:

```bash
pip install pandas numpy matplotlib seaborn
```

2. Place `IPL.csv` in the same directory as the notebook.

3. Open Jupyter Notebook:

```bash
jupyter notebook
```

4. Run the notebook cells in order.

---

## 📈 Future Improvements

* Add player-wise performance dashboards
* Build a prediction model for match outcomes
* Create interactive visualizations using Plotly

---
