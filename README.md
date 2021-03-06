## TOTO analyzer for Singapore Pool v1.0
This is a tool developed as part of the **Python for Data, Ops and Things** course assignment.<br><br>
It collect and analyse data from Singapore pool and is capable of using voice-assisted Alexa
to grab the latest TOTO results.
### Installation of package requirements
pip install -r requirements.txt.

### Examples
```
usage: toto_analyzer.py [-h] [--plotfreq] [--update] [-d DRAW] [-s SET]
                        [-qp QUICKPICK]

optional arguments:
  -h, --help            show this help message and exit
  --plotfreqwc          plot number frequency using word cloud
  --plotfreqbc          plot number frequency using bar chart
  --notin               indicate not to select numbers from any of the
                        selected draws
  --update              update local cache with latest records from Singapore
                        Pool
  -d DRAW, --draw DRAW  return x number of last draws winning numbers
  -s SET, --set SET     return sets of random numbers, can be use together
                        with -qp option
  -qp QUICKPICK, --quickpick QUICKPICK
                        generate a list of random numbers, can be use together
                        with -d option
```
**Update the cache with the latest results from Singapore Pool**
<br>toto_analyzer.py --update
<br>
<br>**Fetch the last drawn 5 results**
<br>toto_analyzer.py -d 5
```
  Thu, 02 Nov 2017 - 7 17 18 30 32 47
  Mon, 30 Oct 2017 - 8 20 30 43 46 48
  Thu, 26 Oct 2017 - 3 10 25 32 36 37
  Mon, 23 Oct 2017 - 2 9 23 35 38 48
  Thu, 19 Oct 2017 - 2 4 15 20 26 28
```
**Plot using wordcloud based on last 15 draws**
<br>toto_analyzer.py -d 15 --plotfreqwc
<p align="center">
  <img src="../master/resource/numcloud.png" width="500"/>
</p>

**Plot using bar chart based on last 15 draws**
<br>toto_analyzer.py -d 15 --plotfreqbc
<p align="center">
  <img src="../master/resource/barchart.png" width="600"/>
</p>

**Generate 5 sets of quick pick using last 15 draw numbers**
<br>toto_analyzer.py -d 15 -qp 6 -s 5
```
Your quick pick numbers are
['44' '34' '28' '2' '36' '19']
['46' '28' '7' '36' '21' '38']
['30' '8' '44' '14' '48' '47']
['4' '20' '32' '47' '36' '21']
['4' '14' '35' '29' '30' '18']
```
**Generate 5 sets of quick pick for numbers not in the last 15 draw**
<br>toto_analyzer.py -d 15 -qp 6 -s 5 --notin
```
Your quick pick numbers are
[16  1 39  5 31 13]
[45  1 16 13  5 39]
[45  1 31  5 39 16]
[13 31 39 45  1 16]
[31 16  5 39 45 13]
```
**Generate 5 sets of quick pick using random numbers**
<br>toto_analyzer.py -qp 6 -s 5
```
Your quick pick numbers are
[33 49 28 43 38 25]
[15  6 21  7 17 11]
[43 14 20  1 18 36]
[23 34 47 49 17 24]
[34 49  2  8 46 43]
```
