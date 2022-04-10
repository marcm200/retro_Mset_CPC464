Locomoive BASIC for Schneider CPC464: Reliable Mandelbrot set's exterior

Using a fixed-point number type based on strings (sign, integer part, fractional part in radix 10), a point seed (complex number) or a seed being a complex interval (having area), the exterior of the classical Mandelbrot set z^2+c in the 2-square was reliably (interval arithmetics, outward rounding) computed using standard escape time with escape radius 10 .


Escaped pixels (white) are truely, mathematically proven, escaping; gray, unclear pixel, but could escape in higher resolution or higher iterations, but might also be interior. Blue pixels just denote a visual border region.

Important variables:
- ps% = 1 => point sampling, seeds are complex numbers;. Upper right white pixel represents 2+2i, other pixels accordingly with grid width and height.
- ps% = 0, seeds are complex intervals tiling the complex plane's 2-square. Upper right white pixel represents the complex interval [2-width..2]+i*[2-height..2]
- maxit%=15: number of maximal iterations
- xe%, ye% length of image. If this number is changed, the grid distances width (pixelw0s,0i$,0f$,1s,1i$,1f$) and height (accordingly) have to be adjusted manually.
- fpf%,fpi%: number of fixed-point digits for the fractional and integer part.

Run on CPC emulator cpcemu v2.4 in real-speed emulation. A 50x50 image for  point seeds took 3 days, with interval seeds 3.5 days.

The code is not optimized (long variable names, not all variables set to the minimal type necessary, interval squaring is performed by interval multiplication, interval multiplication in some cases by optimized flow of calculations, but mostly with the general 8-product approach).

