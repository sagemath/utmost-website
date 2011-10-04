====
News
====

.. begin-recent-news

August 2011
^^^^^^^^^^^
Sage-Enhanced Textbooks
    Rob Beezer `announced
    <http://groups.google.com/group/sage-devel/browse_thread/thread/6b439a44b0794dbb/7f89285396f36b18>`_
    his work on enhancing his `linear algebra textbook
    <http://linear.ups.edu/sage-fcla.html>`_ and also `announced <http://groups.google.com/group/sage-edu/browse_thread/thread/39a89604d56ae837/2a1fe3b7265b38c6>`_
    his work on enhancing Judson's `abstract algebra textbook <http://abstract.ups.edu/sage-aata.html>`_.  Both
    of these projects involved work sponsored by UTMOST.

Embedding Sage in a webpage (beta)
   You can now embed Sage into any webpage!  A beta version of the
   Sage Single Cell server was released.  See the `public beta
   announcement <http://groups.google.com/group/sage-devel/browse_thread/thread/4919d1f6f74d9817/7263cf93d2a40d92>`_
   on the Sage development list.
   
   As an example, click the button below to explore a Taylor
   polynomial
   
   .. raw:: html
     
     <div id="singlecell-interact"><script type="text/code">var('x')
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

   or try whatever Sage computation you want below.
   
   .. raw:: html
    
      <div id="singlecell-test">factorial(30) # edit me</div>

       <script type="text/javascript" src="http://sagemath.org:5467/static/jquery-1.5.min.js"></script>
       <script type="text/javascript" src="http://sagemath.org:5467/embedded_singlecell.js"></script>
       <script type="text/javascript">
    $(function() { // load only when the page is loaded
      var makecells = function() {
      singlecell.makeSinglecell({
          inputLocation: "#singlecell-test",
	  editor: "codemirror",
	  hide: ["computationID","files","messages","sageMode"],
	  replaceOutput: true});
     singlecell.makeSinglecell({
          inputLocation: "#singlecell-interact",
	  template: singlecell.templates.minimal,
	  evalButtonText: "Explore Taylor Polynomials"});
      }
    
      singlecell.init(makecells); // load Single Cell libraries and then
                                  // initialize two Single Cell instances
    
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

