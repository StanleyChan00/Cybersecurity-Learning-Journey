# Tryhackme Pre Security - Module 6: Software Basics 

## Data Representation 
As we know, computers communicate through 1s and 0s, called bits. These bits can be used to represent colors. The following is how colors are specified in graphical programs:

### Representing Colors
All colors come from red, green, and blue. Every color is just a different combination of these colors and by turning off or on one of these colors, we get a distinctly new color. 

We can thus understand this concept as bits. Red, green, and blue can each be represented as a bit of `0` for "off" and `1` for "on". 

For example, `000` would be all 3 colors "off". `101` would be red and blue turned "on" while green is "off. 

Combining all these different combinations of "off" or "on" of each color, we would have a total of 8 different color combinations(2 x 2 x 2) with each color specified by it's own set of 3 bits from `000` to `111`.

<img width="591" height="378" alt="Red Green Blue" src="https://github.com/user-attachments/assets/2885d412-3b87-4f81-988c-71b4a615138f" />

#### More Color Variations:

Now, there are obviously a lot more than 8 colors. So to get more of them, we can alter the "shade" of each of these 3 main colors by having the option to tune the individual brightness of each color, thus resulting in more potential color combinations 

The way that is currently used is having each of the 3 main colors have 8 total bits, resulting in 256 total "shades" of red, 256 total "shades" of green, and 256 total "shades" of blue. 

This now gives us more than 16 million potential color combinations(256 x 256 x 256) each specified by 3 series of 8 bits. Each series of 8 bits is called a **byte** or an octet and each octet gives us the "shade" of each color(red, green, and blue respectively).

## Data Encoding



## Python: Simple Demo



## JavaScript: Simple Demo



## DataBase SQL Basics
