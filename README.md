# Interactive-plots-using-plotly-and-cufflinks-

#importing moduals 
import pandas as pd
import numpy as np
import cufflinks as cf
from plotly import __version__
__version__
from plotly.offline import download_plotlyjs,init_notebook_mode,plot,iplot
init_notebook_mode(connected=True)
cf.go_offline()

#Creating DataFrames using Pandas
df = pd.DataFrame(np.random.randn(100,4),columns=["a","b","c","d"])
df2 = pd.DataFrame({"Category":["A","B","C"],"Values":[33,22,10]})
df3 = pd.DataFrame({"x":[1,2,3,4,5],"y":[10,20,30,20,10],"z":[5,4,3,2,1]})

#Creating line iplot
df.iplot()
df2.iplot()

#creating scatter iplot
df.iplot(kind="scatter",x="a",y="b",mode="markers")

#creating box iplot
df.iplot(kind="box",x="a",y="b")

#createing bar iplot
df2.iplot(kind="bar",x="Category",y="Values",colors="blue")
df.count().iplot(kind="bar")
df.sum().iplot(kind="bar")

#creating surface iplot
df3.iplot(kind="surface",colorscale="rdylbu")
