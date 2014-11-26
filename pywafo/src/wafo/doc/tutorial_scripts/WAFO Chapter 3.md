
CHAPTER3  Demonstrates distributions of wave characteristics
=============================================================

Chapter3 contains the commands used in Chapter3 in the tutorial.

Some of the commands are edited for fast computation.

Section 3.2 Estimation of wave characteristics from data
----------------------------------------------------------
Example 1
~~~~~~~~~~


    speed = 'fast'
    #speed = 'slow'
    
    import wafo.data as wd
    import wafo.misc as wm
    import wafo.objects as wo
    xx = wd.sea() 
    xx[:,1] = wm.detrendma(xx[:,1],len(xx))
    ts = wo.mat2timeseries(xx)
    Tcrcr, ix = ts.wave_periods(vh=0, pdef='c2c', wdef='tw', rate=8)
    Tc, ixc = ts.wave_periods(vh=0, pdef='u2d', wdef='tw', rate=8)


    ---------------------------------------------------------------------------
    AssertionError                            Traceback (most recent call last)

    <ipython-input-12-5b70e90102e6> in <module>()
          8 xx[:,1] = wm.detrendma(xx[:,1],len(xx))
          9 ts = wo.mat2timeseries(xx)
    ---> 10 Tcrcr, ix = ts.wave_periods(vh=0, pdef='c2c', wdef='tw', rate=8)
         11 Tc, ixc = ts.wave_periods(vh=0, pdef='u2d', wdef='tw', rate=8)
    

    c:\pab\workspace\pywafo_svn\pywafo\src\wafo\objects.pyc in wave_periods(self, vh, pdef, wdef, index, rate)
       1980             n = ceil(self.data.size * rate)
       1981             ti = linspace(self.args[0], self.args[-1], n)
    -> 1982             x = stineman_interp(ti, self.args, self.data)
       1983         else:
       1984             x = self.data
    

    C:\Python27\lib\site-packages\matplotlib\mlab.pyc in stineman_interp(xi, x, y, yp)
       2932     x=np.asarray(x, np.float_)
       2933     y=np.asarray(y, np.float_)
    -> 2934     assert x.shape == y.shape
       2935 
       2936     if yp is None:
    

    AssertionError: 



    
