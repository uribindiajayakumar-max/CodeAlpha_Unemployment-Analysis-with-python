import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
# Load dataset (upload your downloaded csv from the task link)
df = pd.read_csv("Unemployment_in_India.csv")
df.columns = df.columns.str.strip() # Clean column spaces
# Date parsing
df["Date"] = pd.to_datetime(df["Date"])
# Visualization: Trend over time
plt.figure(figsize=(10, 5))
sns.lineplot(data=df, x="Date", y="Estimated Unemployment Rate (%)")
plt.title("Unemployment Rate Trend (Highlighting COVID-19 Spike)")
plt.xticks(rotation=45)
plt.show()
# State-wise Unemployment
plt.figure(figsize=(12, 6))
sns.barplot(
 data=df, x="Region", y="Estimated Unemployment Rate (%)", ci=None
)
plt.xticks(rotation=90)
plt.title("Average Unemployment Rate by State")
plt.show()
