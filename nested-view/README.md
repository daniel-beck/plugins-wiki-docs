Older versions of this plugin may not be safe to use. Please review the
following warnings before using an older version:

-   [XXE
    vulnerability](https://www.jenkins.io/security/advisory/2021-08-31/#SECURITY-2411)

**This plugin is up for adoption.** Want to help improve this plugin?
[Click here to learn
more](http://localhost:8085/display/JENKINS/Adopt+a+Plugin "Adopt a Plugin")!

View type to allow grouping job views into multiple levels instead of
one big list of tabs.

This plugin adds a new view type that can be selected when adding job
views. This view does not show any jobs, but rather contains another set
of views. By default, clicking on the view tab for a nested view shows a
list of the subviews it contains (with folder icons). You can also
configure a default subview to bypass this intermediate page and jump
directly to that default view. Now the view tabs across the top show the
views in this nested view, and the job list is for this default subview.
This streamlines the navigation between views, but makes it harder to
find the *Edit View* link for the nested view itself. Once a default
subview has been assigned, navigate to the edit page by first clicking
the plus ("+") icon in the view tabs (for adding a new subview) and then
find the *Edit View* link in the sidepanel.

Note, that starting from 1.10 columns Status and Weather are switched
off by default because of issues with performance, but if you'd like to
have them, just edit your view and add respective columns.

------------------------------------------------------------------------

## Change Log

##### Version 1.14 (November 23, 2013)

-   Improve breadcrumb list behavior
    ([JENKINS-19698](https://issues.jenkins-ci.org/browse/JENKINS-19698),[JENKINS-20616](https://issues.jenkins-ci.org/browse/JENKINS-20616))

##### Version 1.13 (November 5, 2013)

-   Fixed view results to be gray if no jobs were run in subviews yet
    ([issue
    \#17040](https://issues.jenkins-ci.org/browse/JENKINS-17040))
-   Fixed deleting of subviews (it didn't save on disk) ([issue
    \#20382](https://issues.jenkins-ci.org/browse/JENKINS-20382))

##### Version 1.12 (October 30, 2013)

-   Fixed view results (aggregating of subviews and jobs) to follow the
    correct priority - if at least one job is red, then the view will be
    red ([issue
    \#19716](https://issues.jenkins-ci.org/browse/JENKINS-19716))

##### Version 1.11 (September 25, 2013)

-   Fixed creation of subviews if Nested View is the default one
    ([JENKINS-17041](https://issues.jenkins-ci.org/browse/JENKINS-17041))
-   Support checking duplicate names with jenkins 1.512 or newer
    ([JENKINS-18053](https://issues.jenkins-ci.org/browse/JENKINS-18053))

##### Version 1.10 (April 7, 2013)

-   Added an ability to remove or add Weather and Status columns which
    speeds up nested views
    ([JENKINS-17352](https://issues.jenkins-ci.org/browse/JENKINS-17352))

##### Version 1.9 (August 16, 2012)

-   Improved performance and accuracy when computing worst result and
    health for large views
-   add support for hierarchical job model (ex : cloudbees folder
    plugin)
-   display grey icon when no nested content has been built

##### Version 1.8 (Jul 28, 2011)

-   Properly check for duplicate names within the current nested view
    when creating a new view (in Jenkins 1.416 or newer).
-   Ignore disabled project when calculating worst build result in a
    nested view.
    ([JENKINS-8922](https://issues.jenkins-ci.org/browse/JENKINS-8922))

##### Version 1.7 (Feb 25, 2011)

-   Rerelease 1.6 to properly set required Jenkins version.

##### Version 1.6 (Feb 16, 2011)

-   Show status icon for each view, representing the worst result of any
    job in that view.
    ([JENKINS-7124](https://issues.jenkins-ci.org/browse/JENKINS-7124))
-   Fix link in empty nested view to be a link instead of raw HTML.
    ([JENKINS-7862](https://issues.jenkins-ci.org/browse/JENKINS-7862))

##### Version 1.5 (Oct 20, 2010)

-   Update to work with Hudson 1.381 or higher.
    ([JENKINS-7815](https://issues.jenkins-ci.org/browse/JENKINS-7815))
-   Calculate view-health for a nested view by recursing into its
    subviews.
    ([JENKINS-7125](https://issues.jenkins-ci.org/browse/JENKINS-7125))
-   Export nested view details via Remote API.
    ([JENKINS-7489](https://issues.jenkins-ci.org/browse/JENKINS-7489))
-   Don't allow setting a default subview for a nested view that is the
    Hudson default view, as this prevents access to other top level view
    tabs.
    ([JENKINS-7362](https://issues.jenkins-ci.org/browse/JENKINS-7362))

##### Version 1.4 (Jul 12, 2010)

-   Update to work with Hudson 1.366 or higher.

##### Version 1.3 (Jun 16, 2010)

-   Sort subviews alphabetically.
    ([JENKINS-6757](https://issues.jenkins-ci.org/browse/JENKINS-6757))
-   Russian translation.

##### Version 1.2 (May 27, 2010)

-   Add weather icons in nested view.
    ([JENKINS-6235](https://issues.jenkins-ci.org/browse/JENKINS-6235))

##### Version 1.1 (Mar 22, 2010)

-   Spanish translation.

##### Version 1.0 (Jan 21, 2010)

-   Initial release.
