# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Date:
# AIM:
To implement ARMA model in python.
# ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000 data points using the ArmaProcess class. Plot the generated time series and set the title and x-axis limits.
4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000 data points using the ArmaProcess class. Plot the generated time series and set the title and x-axis limits.
6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using plot_acf and plot_pacf.


# PROGRAM:
```
Developed by: Challa Sandeep
Reg No: 212221240011
```
~~~
from pandas import read_csv
from pandas import datetime
from matplotlib import pyplot
from pandas.plotting import autocorrelation_plot
from pandas import DataFrame
from statsmodels.tsa.arima_model import ARIMA
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
from statsmodels.tsa.arima_process import ArmaProcess
import matplotlib.pyplot as plt
import numpy as np
import warnings
warnings.filterwarnings('ignore')
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['figure.figsize'] = [10, 7.5]

ar1 = np.array([1,0.33])
ma1 = np.array([1,0.9])
ARMA_1 = ArmaProcess(ar1,ma1).generate_sample(nsample = 1000)
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_1)
plot_pacf(ARMA_1)
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=10000)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
~~~
# OUTPUT:
# SIMULATED ARMA(1,1) PROCESS:

![4 1](https://github.com/shaikSameerbasha5404/TSA_EXP4/assets/118707756/0eba85f9-28cd-4a19-a160-9ce864819ea9)


# Partial Autocorrelation
![4 2](https://github.com/shaikSameerbasha5404/TSA_EXP4/assets/118707756/a05b48a6-ddf4-4cbc-87af-366b1f125595)

# Autocorrelation

![4 3](https://github.com/shaikSameerbasha5404/TSA_EXP4/assets/118707756/2ca4ba42-224d-4669-8849-be5cc4cb3821)


# SIMULATED ARMA(2,2) PROCESS:
![4 4](https://github.com/shaikSameerbasha5404/TSA_EXP4/assets/118707756/9bfc35bd-e28b-4b29-ab2e-e4f6fb0a1d31)

# Partial Autocorrelation

![4 5](https://github.com/shaikSameerbasha5404/TSA_EXP4/assets/118707756/399afcea-136e-4c6c-8a31-3223599f2b97)


# Autocorrelation
![4 6](https://github.com/shaikSameerbasha5404/TSA_EXP4/assets/118707756/723c880b-9823-48a0-a289-7ca79ab9f2fe)

# RESULT:
Thus, a python program is created to fir ARMA Model successfully.
