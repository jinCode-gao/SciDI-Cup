# SciDI-Cup

1.Background:
The main objective of this contest is to find two short time scale rare celestial light events, microgravitational lensing candidate and stellar flare candidate, from the time-domain astronomical big data samples collected by GWAC.The properties of the data provided by the competition are time domain data (optical curves) containing time information and celestial object luminosity information.The corresponding calculation task is to identify the time series containing the events of the short-time scale rare celestial bodies (that is, an anomalous sub-sequence).The candidate body of microgravitational lens shows a process in which the celestial body's luminosity gradually brightens and then gradually returns to normal, and the changes are partially symmetrical, as shown in Figure 1.FIG. 3 is an example of the optical transformation curve including microgravitational lens candidates collected by GWAC (Reverse Y coordinate axis, FIG. 4-6, Magnorm is magnitude, the smaller magnitude, the stronger the luminosity of celestial bodies).Stellar emission candidates show a process of rapid brightening and slow recovery of celestial bodies, and the changes are partly asymmetric, as shown in FIG. 2.FIG. 4 is an example of the light transformation curve including stellar flare candidates collected by GWAC.It is worth noting that stellar outburst may not only occur once, but may occur twice or more in succession, as shown in FIG. 5, which is an example of the phototransformation curve of two consecutive stellar outburst candidates collected by GWAC.

2.Install:
Python3.7
Install the outlier.py and main.py in the same directory.
The outlier.py file is an anomaly detection tools, contain the following functions: through gaussian distribution of the suspected abnormal points of time series data, meaning abnormal point confidence, by detecting algorithm find the suspected abnormal interval, suspected abnormal interval numerical analysis including range scale, anomaly gradient size range, abnormal interval extremum average magnitude and point of difference, judge suspected abnormal confidence interval.
The main function reads and encapsulates the match data, and calls the outlier.py method to traverse the data set for exception detection.

3.Maintainers:
Gao Jin,Liu Tingzhen,Zhou Tong

4.Contributors:
Gao Jin,Liu Tingzhen,Zhou Tong

5.License:
MIT
