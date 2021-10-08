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

to_date=dt.date.today()
from_date=to_date-dr.relativedelta(days=365)
print(from_date,to_date)
tradingsymbol='TITAN'
df=gh(tradingsymbol,from_date,to_date)
df['Date']=df.index
