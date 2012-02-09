====
News
====

.. begin-recent-news

August 2011
^^^^^^^^^^^

AIM Open Textbook Initiative
    American Institute of Mathematics has launched its `Open Textbook
    Initiative <http://aimath.org/textbooks/>`_.  This initiative will
    review and provide links to high-quality open-source textbooks.
    This initiative is supported in part by UTMOST.

Sage-Enhanced Textbooks
    Rob Beezer `announced
    <http://groups.google.com/group/sage-devel/browse_thread/thread/6b439a44b0794dbb/7f89285396f36b18>`_
    his work on enhancing his `linear algebra textbook
    <http://linear.ups.edu/sage-fcla.html>`_ and also `announced <http://groups.google.com/group/sage-edu/browse_thread/thread/39a89604d56ae837/2a1fe3b7265b38c6>`_
    his work on enhancing Judson's `abstract algebra textbook <http://abstract.ups.edu/sage-aata.html>`_.  Both
    of these projects involved work sponsored by UTMOST.

Embedding Sage in a webpage (beta)
   You can now embed Sage into any webpage!  A beta version of the
   Sage Cell server was released.  See the `public beta
   announcement <http://groups.google.com/group/sage-devel/browse_thread/thread/4919d1f6f74d9817/7263cf93d2a40d92>`_
   on the Sage development list.
   
   As an example, click the button below to explore a Taylor
   polynomial
   
   .. raw:: html
     
    <div id="sagecell-interact"><script type="text/code">var('x')
    x0  = 0
    f(x)   = sin(x)*e^(-x)
    p   = plot(f,(x,-1,5), thickness=2)
    dot = point((x0,f(x=x0)),pointsize=80,rgbcolor=(1,0,0))
    @interact
    def _(order=(1..12)):
       ft = f.taylor(x,x0,order)
       pt = plot(ft,(x,-1, 5), color='green', thickness=2)
       html('$f(x)\;=\;%s$'%latex(f(x)))
       html('$\hat{f}(x;%s)\;=\;%s+\mathcal{O}(x^{%s})$'%(x0,latex(ft(x)),order+1))
       show(dot + p + pt, ymin = -.5, ymax = 1)
    </script></div>

   or generate graph paper (including a pdf)

   .. raw:: html
     
        <div id="sagecell-graphpaper"><script type="text/code">html("<h3>Graph Paper Generator</h3>")
        import matplotlib
        @interact(layout=[['xmin','xmax'],['ymin','ymax'],['nolab','xlab'],['gridlines','ylab']])
        def doit(xmin=-4,xmax=4,ymin=-4,ymax=4,nolab=('labels',True),xlab=('x ticks',True),ylab=('y ticks',True),gridlines=('gridlines',True)):
         if xlab:
             xlabels=[xmin+i for i in range(0,xmax-xmin+1)]
         else:
             xlabels=[]
         if ylab:
             ylabels=[ymin+i for i in range(0,ymax-ymin+1)]  
         else:
             ylabels=[]
         p=plot(0,(x,xmin,xmax),ymin=ymin,ymax=ymax,ticks=[xlabels,ylabels],color='black', aspect_ratio=1,
                gridlines=gridlines, gridlinesstyle=dict(linestyle='--',color='gray'))
         if nolab:
             show(p)
             html('Click on link below to download PDF version.')
             p.save("graph.pdf")
         else:
             p.show(tick_formatter=(matplotlib.ticker.NullFormatter(),matplotlib.ticker.NullFormatter()))
             html('Click on link below to download PDF version.')
             p.save("graph.pdf",tick_formatter=(matplotlib.ticker.NullFormatter(),matplotlib.ticker.NullFormatter())) 
        </script></div>
 

   or try whatever Sage computation you want below.
   
   .. raw:: html
    
      <div id="sagecell-test">factorial(30) # edit me</div>

       <script type="text/javascript" src="http://sagemath.org:5467/static/jquery-1.7.1.min.js"></script>
       <script type="text/javascript" src="http://sagemath.org:5467/embedded_sagecell.js"></script>
       <script type="text/javascript">
    $(function() { // load only when the page is loaded
      var makecells = function() {
      sagecell.makeSagecell({
          inputLocation: "#sagecell-test",
	  editor: "codemirror",
	  hide: ["computationID","files","messages","sageMode"],
	  replaceOutput: true});
     sagecell.makeSagecell({
          inputLocation: "#sagecell-interact",
	  template: sagecell.templates.minimal,
	  evalButtonText: "Explore Taylor Polynomials"});
     sagecell.makeSagecell({
          inputLocation: "#sagecell-graphpaper",
	  template: sagecell.templates.minimal,
	  evalButtonText: "Make graphing paper"});
      }
    
      sagecell.init(makecells); // load Sage Cell libraries and then
                                  // initialize two Sage Cell instances
    
      });
      </script>



June 2011
^^^^^^^^^

Sage Education Days 3, 16--18 Jun 2011
    We had our first UTMOST conference in Seattle with the test site
    teacher-authors for the 2011-2012 academic year.  See the
    `conference homepage <http://wiki.sagemath.org/education3>`_ for
    details, links to videos of the talks, etc.

.. end-recent-news

July 2010
^^^^^^^^^

Grant awarded
    The UTMOST proposal was awarded a grant!

