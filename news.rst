====
News
====

.. begin-recent-news

June 2014
^^^^^^^^^

Sage Education Days, June 16--18
    `Sage Edu Days 6 <http://wiki.sagemath.org/education6>`__ will be
    held June 16--18 at the University of Washington in Seattle.  See
    the website for schedule and videos of talks.

    Anyone with an interest in the use of Sage in educational settings
    is welcome to attend.  The focus will primarily be on undergraduate
    mathematics, but will not be limited to just that area.

    There will also be a `developer conference
    <http://wiki.sagemath.org/days58>`__ happening that whole week.

March 2014
^^^^^^^^^^

Sage Cell Server
    In March 2014, the Sage Cell Server had an average of 1986
    computations per day, about 100 more computations per day than in
    February 2014.  The service was visited by users in 158 countries
    (about half coming from United States, 25% from Europe, and
    10% from Asia).  The top city accessing the service was Tacoma, WA
    (no doubt due to Rob Beezer's online linear algebra textbook using
    it), followed by Omaha, NE, Ottawa, Hartford, CN, and Fargo, ND.

SageMathCloud
    In March 2014, about 40,000 projects were modified.  At the end of
    March, there were around 28,500 accounts (with about 150 accounts being
    created each day) and around 43,500 total projects.  See `this page
    <http://boxen.math.washington.edu/home/schilly/salvus/stats/stats.html>`__
    for more graphs and statistics.

January 2014
^^^^^^^^^^^^

Joint Mathematics Meetings, January 15--18
    The UTMOST team presented a poster on this project at the NSF
    UTMOST poster session

    Several UTMOST collaborators talked in sessions, including the
    MAA Open Textbook session (Tom Judson/Rob Beezer) and in the MAA
    Online Resources session (Jason Grout).

    The Sage project also had a successful booth in the exhibit hall, which introduced
    many people to both the SageMathCloud and the Sage Cell Server


June 2013
^^^^^^^^^

Sage Education Days, June 19--21
    `Sage Edu Days 5 <http://wiki.sagemath.org/education5>`__ will be
    held June 19--21 at the University of Washington in Seattle.  See
    the website for schedule and videos of talks.

    Anyone with an interest in the use of Sage in educational settings
    is welcome to attend.  The focus will primarily be on undergraduate
    mathematics, but will not be limited to just that area.

    There will also be a `developer conference
    <http://wiki.sagemath.org/days48>`__ happening that whole week,
    with the Sage Cloud as the theme.

.. end-recent-news
 
June 2012
^^^^^^^^^

Sage Education Days, June 13--21
    `Sage Edu Days 5 <http://wiki.sagemath.org/education4>`__ will be
    held June 13-15 at the University of Washington in Seattle.

    Anyone with an interest in the use of Sage in educational settings
    is welcome to attend.  The focus will primarily be on undergraduate
    mathematics, but will not be limited to just that area.

    There will also be a `developer conference
    <http://wiki.sagemath.org/days41>`__ happening that whole week,
    with the Sage notebook as the theme.

January 2012
^^^^^^^^^^^^

Joint Meetings
    We had a booth in the TUES poster session, and the Sage booth in the
    conference hall was a big hit as well.

August 2011
^^^^^^^^^^^

Mathfest
    We had a very successful booth that we shared with the `Webwork <http://webwork.maa.org/>`__ folks.

AIM Open Textbook Initiative
    American Institute of Mathematics has launched its `Open Textbook
    Initiative <http://aimath.org/textbooks/>`__.  This initiative will
    review and provide links to high-quality open-source textbooks.
    This initiative is supported in part by UTMOST.

Sage-Enhanced Textbooks
    Rob Beezer `announced
    <http://groups.google.com/group/sage-devel/browse_thread/thread/6b439a44b0794dbb/7f89285396f36b18>`__
    his work on enhancing his `linear algebra textbook
    <http://linear.ups.edu/sage-fcla.html>`__ and also `announced <http://groups.google.com/group/sage-edu/browse_thread/thread/39a89604d56ae837/2a1fe3b7265b38c6>`__
    his work on enhancing Judson's `abstract algebra textbook <http://abstract.ups.edu/sage-aata.html>`__.  Both
    of these projects involved work sponsored by UTMOST.

Embedding Sage in a webpage (beta)
   You can now embed Sage into any webpage!  A beta version of the
   Sage Cell server was released.  See the `documentation
   <http://sage.math.washington.edu/home/jason/sagecell/embedding.html>`__
   for embedding a computation.
   
   As an example, click the button below to explore a Taylor
   polynomial
   
   .. raw:: html

      <script type="text/javascript" src="http://aleph.sagemath.org/static/jquery.min.js"></script>
      <script type="text/javascript" src="http://aleph.sagemath.org/embedded_sagecell.js"></script>

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
      <script>
      $(function () {
          sagecell.makeSagecell({inputLocation:  '#sagecell-interact',
                                 template: sagecell.templates.minimal,
                                 evalButtonText: "Explore Taylor polynomials"})})
      </script>

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
        <script>
        $(function () {
            sagecell.makeSagecell({inputLocation:  '#sagecell-graphpaper',
	                           template: sagecell.templates.minimal,
                                   evalButtonText: "Make graphing paper"})})
        </script>
 

   or try whatever Sage computation you want below.
   
   .. raw:: html
    
      <div id="sagecell-test">factorial(30) # edit me</div>

      <script>
      $(function () {sagecell.makeSagecell({
            inputLocation: '#sagecell-test', 
            'hide': ['files']})})
      </script>



June 2011
^^^^^^^^^

Sage Education Days 3, 16--18 Jun 2011
    We had our first UTMOST conference in Seattle with the test site
    teacher-authors for the 2011-2012 academic year.  See the
    `conference homepage <http://wiki.sagemath.org/education3>`__ for
    details, links to videos of the talks, etc.


July 2010
^^^^^^^^^

Grant awarded
    The UTMOST proposal was awarded a grant!

