# Matplotlib

     Types of Plots
1.	Linear Plot
2.	Scatter Plot
3.	Bar Plot
4.	Stem Plot
5.	Step Plot
6.	Hist Plot
7.	Box Plot
8.	Pie Plot
9.	Fill_Between Plot

plt.plot(x, y)  -> Creates the line graph
plt.show()      -> Shows the graph

Bar Graph
1.	Applying color directly using variable
C_Var = ['r','g','b','y]      -> Giving the color for different elements of the graph
 plt.bar(x, y, C_Var)          -> Plots/Creates the bar graph with the colors mentioned for the bars
 Note the color order will repeat once all the starting bars takes the color
 

2.	Applying color through color parameter
a = [1,2,3,4,5]
b = [2,4,6,8,10]
c = ['r','g']
plt.bar(a,b, color=c)
 
3.	Add labels and title to chart
x = ["Python", "Java", "C", "C++"]
y = [85, 82, 60, 72]

plt.bar(x,y)
plt.xlabel("Languages")
plt.ylabel("Popularity")
plt.title("Languages V/s Popularity")
plt.show()
 

4.	Add border to bar
x = ["Python", "Java", "C", "C++"]
y = [85, 82, 60, 72]

plt.bar(x,y, edgecolor='r', linewidth=2, linestyle=":")

plt.xlabel("Languages")
plt.ylabel("Popularity")
plt.title("Languages V/s Popularity")
plt.show()
 
5.	General functions
fontsize  - can be given for axis, scale values, legend
plt.xlabel("Languages", fontsize=10)  -> Axis Label
plt.ylabel("Count", fontsize=10)  -> Axis Label
plt.xticks(p+0.2,x, fontsize=8)  -> Axis Values
plt.yticks(fontsize=8)  -> Axis Values
plt.legend(fontsize=8)  -> Legends

Width - can be given the bar element
plt.bar(x, y, width=0.4, align='center', label='Popularity')

axis alignment    - axis can be aligned to edge or center
plt.bar(x, y, width=0.4, align='center')


bar's additional properties - border color, border size and border style
plt.bar(x,y, edgecolor='r', linewidth=2, linestyle=":")

alpha parameter(0 to 1) for blurring
plt.bar(x, y, alpha=0.4)

legend - Need to mentioned at the graph creation and has to be called separately
plt.bar(x, y , label='Popularity')  -> Creating legent
plt.legend()  -> Calling legent

6.	Multiple charts on same axis
import numpy as np
x = ["Python", "Java", "C", "C++"]
y = [85, 82, 60, 72]
z = [20, 40, 30, 50]

p = np.arange(len(x))
p1 = p+0.4

plt.bar(x, y, width=0.4, label="popularity", align='center')
plt.bar(x, z, width=0.4, label="users", align='center')


plt.xlabel("Languages", fontsize=10)
plt.ylabel("Count", fontsize=10)

* Adding legends, changing fontsize
plt.xticks(x, fontsize=8)
plt.yticks(fontsize=8)
plt.legend(fontsize=8)
plt.title("Languages usage - Stacked Bar Graph")
plt.show()
 

7.	Stacked bar chart one next to another, through alignment using alpha
import numpy as np
x = ["Python", "Java", "C", "C++"]
y = [85, 82, 60, 72]
z = [20, 40, 30, 50]

p = np.arange(len(x))
p1 = p+0.4

plt.bar(p, y, width=0.4, label="popularity", align='center', alpha=0.4)
plt.bar(p1, z, width=0.4, label="users", align='center')

plt.xlabel("Languages", fontsize=10)
plt.ylabel("Count", fontsize=10)


plt.xticks(p+0.2,x, fontsize=8)
plt.yticks(fontsize=8)
plt.legend(fontsize=8)
plt.title("Languages usage - Bar Graph")
plt.show()
 

8.	Horizontal Stacked bar graph
x = ["Python", "Java", "C", "C++"]
y = [85, 82, 60, 72]
z = [20, 40, 30, 50]

p = np.arange(len(x))
p1 = p+0.4

plt.barh(x, y,label="popularity", align='center')
plt.barh(x, z,label="users", align='center')

plt.xlabel("Languages", fontsize=10)
plt.ylabel("Count", fontsize=10)


plt.yticks(x, fontsize=8)
plt.xticks(fontsize=8)
plt.legend(fontsize=8)
plt.title("Languages usage - Horizontal Bar Graph")
plt.show()
 

Scatter Plot 
* Plotting the scatter plot
plt.scatter(x, y)

* Changing the size(s) and color(c) of the buble by listing colors and values which are having same count as the x/y parameters count
* alpha gives the blurrness
plt.scatter(Day, Num, c=var_color, s=var_size, alpha=between 0 to 1)

* We can dynamically create the colurs based on the cmap parameter
size = np.array(y)*50
plt.scatter(x, y, c=size, cmap='Accent')
 

Histplot

Code to import matplotlib 
-> import matplotlib.pyplot as plt
Only one parameter is enough to plot histogram
We can create bin of required size and assighn to bins parameter  
-> plt.hist(num, bins=var_bin_range)
Can also add the line to the area  
-> plt.hist(num, color='b', edgecolor='r', linewidth=2, linestyle=":")
Alighn the hist are to left/right/mid 
-> plt.hist(num, align='left')
Types of hist (step, stepfilled)  
-> plt.hist(num, histtype='step')
Types of orientation(horizontal/vertical) 
-> plt.hist(num, orientation='horizontal')
Add additinonal axis line along vertical direction 
-> plt.axvline(50, color='r', label='limit')
Add additinonal axis line along vertical direction 
-> plt.axhline(7, color='b', label='max')
Grid can be added 
-> plt.grid()
Normal table can be converted to log table using 
-> plt.hist(num, log=True)
 

Pie Chart

Only one parameter is enough to pie graph
Syntax - plt.pie(x)
By creating variable and adding it to labels parameter will show labels on chart  
-> plt.pie(num, labels=var_label)

Exploding the part of the pie, by creating exploading value and assigning it to explode parameter 
-> exp_var = [0.1, 0, 0, 0]
     plt.pie(num, labels=lang, autopct="%i%%", explode=exp_var)

Adding percentage to the chart    
-> plt.pie(num, labels=var_label, autopct="%0.1f%%") 
* (Gives percentage with 2 digits after deciamal)
* (autopct="%0.2f%%") - Gives percentage with 1 digit after decimal
* (autopct="%i%%"r) - Gives percentage with no digit after decimal

Add shadow to the pie chart   
-> plt.pie(num, labels=lang, shadow=True)

Changing the size of the chart by radius parameter    
-> plt.pie(num, labels=lang, radius=0.8)

Label distance, starting angel of chart, and the text properties    
-> plt.pie(num, labeldistance=1.1, startangle=90, textprops={"fontsize": 14, "color":'w'})

legend can be placed on either of 1 corner  
-> plt.legend(loc=4)

Creating Dougnut chart    
-> 1st create actual pie chart and give radius, 2nd create dummy chart with radius less than previous one and color as white
1st Step - plt.pie(num, labels=lang, radius=1)
2nd Step - plt.pie([1], radius=0.5, colors='w')

 


Stem Plot

Stem Plot - plots a line with dot/marker at the value point
Syntax - plt.stem(x, y)

markerfmt - properties related to marker is passed to this argument shape followed by color
plt.stem(x, y1, markerfmt="sr")   -> Square Red
plt.stem(x, y1, markerfmt="hm")   -> Hexagon magenta
plt.stem(x, y1, markerfmt="pm")   -> Pentagon blue 
plt.stem(x, y1, markerfmt="ob")   -> Circle blue
plt.stem(x, y1, markerfmt="*b")   -> Star blue
plt.stem(x, y1, markerfmt="+b")   -> Plus blue
plt.stem(x, y1, markerfmt="-m")   -> Gives Line (Connects the points)
plt.stem(x, y1, markerfmt=":m")   -> Gives dotted line (Connects the points)

The chart can be oriented horizontall/vertically  
-> plt.stem(x, y1, orientation='horizontal')

The bottom line starting value(bottom) and the color of bottom line(basefmt) is modified   
-> plt.stem(x, y1, bottom=1, basefmt='b')

The line properties can also be changed using 
-> plt.stem(x, y, linefmt=":g")

Multiple variable within same graph   
-> plt.stem(x, y1), plt.stem(x, y2)

We can add 2 different baseline for graph
x = ['A','B', 'C','D','E']
y1 = [2,5,1,6,9]
y2 = [-2,-4,4,-3,5]

plt.stem(x, y1, label="Level 1", markerfmt="sr", bottom=0.5)
plt.stem(x, y2, label="Level 2", linefmt=":g", markerfmt="*", bottom=-0.5)
plt.legend()
plt.show()
 

Box and Whisker Plot

Syntax
plt.boxplot(var)
plt.show()

Plot multiple box plots and add label 
-> plt.boxplot([Var1, Var2], labels=["Var1 name", "Var2 name"])

Plots box with notch shape at center  
-> plt.boxplot(Var1, notch=True)

Alighn the plot horizontally, change the width of the box, fill the box 
->  plt.boxplot(new_sal, vert=False, widths=0.1, patch_artist=True)

Shows the mean within the box plot  
-> plt.boxplot(new_sal, showmeans=True)

Chnage the shape and color of the outlier 
->  plt.boxplot(var, sym="color symbol")
* Different colors are b,r, g, m (blue, red, green, magenta)
* Different symbols are o, +, |

Change the color of boxline, cap, whisker 
-> plt.boxplot(var, boxprops={"color":'r'}, capprops={"color":'b'}, whiskerprops={'color':'m'})
 

Stack Plot

Stack Plot - plots the area for the given values
Syntax - plt.stack(axis_within boundary, [area], labels=['area'], colors=[])

plt.stackplot(x, [area1, area2, area3], baseline='zero') 
-> Baseline parameter is used for starting the area
baseline = 'zero' -> Starts from 0
baseline = 'sym' -> Starts from -ve axis
baseline = 'wiggle' -> Gives proper visual

 

Step Plot

Stem Plot - Plots the point that intersects both x axis and y axis
Syntax - plt.step(x, y)

plt.step(x, y, color='r', marker='s', ms=8, mfc='b')
color -> Color of the line
marker -> point/marker of specified shape [s -> square, o -> circle, * -> star, + -> Plus]
ms -> marker size
mfc -> marker face color [b -> blue, m-> magenta, r -> red, b -> blue]
 




Other Parameters

1.	fill_between -> is used for filling or highlighting the area
Syntax - plt.fill_between(x, y)

plt.fill_between(x=[2,4], y1=2, y2=4 )    -> Create Square using two different points in y axis
plt.fill_between(x=[2,4], y1=[4,2])   -> Create shape using one point in y axis

Fill the area/highlight the are based on where condition (Note for this the axis need to be in array format)
x = np.array([1,2,3,4,5])
y = np.array([2,4,3,2,5])
plt.fill_between(x, y,  color='g',where = (x>=2) & (x<4), alpha=0.4)	

2.	Subplot - Used for plotting multiple plots
Syntax plt.subplot(row, column, position)						
Ex - x = [1,2,3,4,5]
y = [2,3,5,4,6]

plt.subplot(2,2,1)
plt.plot(x, y)
plt.xlabel('X-Axis')


plt.subplot(2,2,2)
plt.pie([1])

plt.subplot(2,2,3)
plt.pie([20, 40, 30, 60, 15])

plt.subplot(2,2,4)
x1=['a','s','d','f']
y1=[30, 20, 40, 15]
plt.bar(x1, y1)
plt.xlabel('Labels')


plt.show()
 															
3.	Savefig - Saves the plotted graph as image
Syntax - plt.savefig(filename)	
4.	Axis of a figure can be given in 3 ways
1 plt.xticks(values)
2 plt.xlim(start, end)
3 plt.axis([x_start, x_end, y_start, y_end])

5.	Tex parameters
plt.xlabel('X - Axis', fontsize=14)   -> Change font size of label

Synatax (Add text at specified intersecting region of x and y) - plt.text(x,y, Text, bbox=dict(facecolor=value, edgecolor=value))
Ex - plt.text(1.5, 4, "Sample Text", style='italic', bbox=dict(facecolor="yellow", edgecolor='red'))

Syntax (Points towards required x,y intersecting region) - plt.annotate(text, xy=(x_position,y_position), xytext=(x_position,y_position), arrowprops=dict(facecolor='black'))
plt.annotate('Pointing the value', xy=(3,5), xytext=(3,3), arrowprops=dict(facecolor='black'))

Syntax (Add box and other parameters to legend) - plt.legend([text], loc=n, facecolor=color, edgecolor=color, framealpha=value(0 to 1), shadow=True)
plt.legend(['Legend'], loc=2, facecolor="blue", edgecolor='red', framealpha=0.1, shadow=True)	