```python
import pandas as pd

# Sample data representing historical currency prices
data = {'Date': ['2022-01-01', '2022-01-02', '2022-01-03', '2022-01-04', '2022-01-05'],
        'Price': [100, 110, 105, 120, 115]}

df = pd.DataFrame(data)

# Calculate daily price changes
df['Price Change'] = df['Price'].diff()

# Identify patterns based on price changes
df['Pattern'] = 'Stable'
df.loc[df['Price Change'] > 0, 'Pattern'] = 'Upward'
df.loc[df['Price Change'] < 0, 'Pattern'] = 'Downward'

print(df)
