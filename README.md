# Market
Market

plotyly Documentation

https://plotly.com/python/candlestick-charts/

Adding a Column in Dataframe
df['new_col'] = range(1, len(df) + 1)

Exrtracting Data from NSE

from nsepy import get_history as gh
import datetime as dt
import dateutil.relativedelta as dr


to_date=dt.date.today()
from_date=to_date-dr.relativedelta(days=365)
print(from_date,to_date)
tradingsymbol='TITAN'
data=gh(tradingsymbol,from_date,to_date)



Candle Stick Graph


import plotly.graph_objects as go



from nsepy import get_history as gh
import datetime as dt
import dateutil.relativedelta as dr
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn import metrics
import numpy as np
import pandas as pd
from datetime import datetime
import plotly.graph_objects as go



to_date=dt.date.today()
from_date=to_date-dr.relativedelta(days=365)
print(from_date,to_date)
tradingsymbol='TITAN'
df=gh(tradingsymbol,from_date,to_date)
df['Date']=df.index

fig = go.Figure(data=[go.Candlestick(x=df['Date'],
                open=df['Open'],
                high=df['High'],
                low=df['Low'],
                close=df['Close'])])

fig.update_layout(
    title='Titan Price Movement',
    yaxis_title='Price',
)

fig.show()

