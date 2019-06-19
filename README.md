# Go Module Example


## Problems that Dependency Management Tries To Solve

### Package Moves On, but Your App or Service Didn't

### Getting a Version of a Package that Your App Or Service Isn't Expecting

Packages can iterate quickly.

### Dependency Hell

Your app or service has packages it depends on. Each of those packages may
themselves have specific versions of packages that they depend on. Below is
a visualization of both Packages A and B requiring Package C, but they
require different versions of Package C.

```
       +------------------+
       |                  |
       |  App or Service  |
       |                  |
       +--+------------+--+
          |            |
          |            |
+---------+---+    +---+---------+
|             |    |             |
|  Package A  |    |  Package B  |
|     v2      |    |     v4      |
|             |    |             |
+-------+-----+    +--------+----+
        |                   |
+-------+-----+    +--------+----+
|             |    |             |
|  Package C  |    |  Package C  |
|  ** v6 **   |    |  ** v3 **   |
|             |    |             |
+-------------+    +-------------+
```
