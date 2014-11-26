
CHAPTER3  Demonstrates distributions of wave characteristics
=============================================================

Chapter3 contains the commands used in Chapter3 in the tutorial.

Some of the commands are edited for fast computation.

Section 3.2 Estimation of wave characteristics from data
----------------------------------------------------------
Example 1
~~~~~~~~~~

    %matplotlib inline
    import matplotlib.pyplot as plt


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

    C:\Anaconda\lib\site-packages\wafo-0.1.2-py2.7.egg\wafo\spectrum\core.py:35: UserWarning: Compile the c_library.pyd again!
      warnings.warn('Compile the c_library.pyd again!')
    C:\Anaconda\lib\site-packages\wafo-0.1.2-py2.7.egg\wafo\spectrum\core.py:40: UserWarning: Compile the cov2mod.pyd again!
      warnings.warn('Compile the cov2mod.pyd again!')
    


    plt.plot(Tc, label='Tc')
    plt.legend()




    <matplotlib.legend.Legend at 0x15a63a90>




![png](WAFO%20Chapter%203_files/WAFO%20Chapter%203_3_1.png)



    plt.plot(ixc, label='ixc')
    plt.legend()




    <matplotlib.legend.Legend at 0x15a95f98>




![png](WAFO%20Chapter%203_files/WAFO%20Chapter%203_4_1.png)



    
