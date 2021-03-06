cola Report for Hierarchical Partitioning - 'TCGA_PCPG_methylation'
==================

**Date**: 2021-07-22 16:13:31 CEST, **cola version**: 1.9.4

----------------------------------------------------------------

<style type='text/css'>

body, td, th {
   font-family: Arial,Helvetica,sans-serif;
   background-color: white;
   font-size: 13px;
  max-width: 800px;
  margin: auto;
  margin-left:210px;
  padding: 0px 10px 0px 10px;
  border-left: 1px solid #EEEEEE;
  line-height: 150%;
}

tt, code, pre {
   font-family: 'DejaVu Sans Mono', 'Droid Sans Mono', 'Lucida Console', Consolas, Monaco, 

monospace;
}

h1 {
   font-size:2.2em;
}

h2 {
   font-size:1.8em;
}

h3 {
   font-size:1.4em;
}

h4 {
   font-size:1.0em;
}

h5 {
   font-size:0.9em;
}

h6 {
   font-size:0.8em;
}

a {
  text-decoration: none;
  color: #0366d6;
}

a:hover {
  text-decoration: underline;
}

a:visited {
   color: #0366d6;
}

pre, img {
  max-width: 100%;
}
pre {
  overflow-x: auto;
}
pre code {
   display: block; padding: 0.5em;
}

code {
  font-size: 92%;
  border: 1px solid #ccc;
}

code[class] {
  background-color: #F8F8F8;
}

table, td, th {
  border: 1px solid #ccc;
}

blockquote {
   color:#666666;
   margin:0;
   padding-left: 1em;
   border-left: 0.5em #EEE solid;
}

hr {
   height: 0px;
   border-bottom: none;
   border-top-width: thin;
   border-top-style: dotted;
   border-top-color: #999999;
}

@media print {
   * {
      background: transparent !important;
      color: black !important;
      filter:none !important;
      -ms-filter: none !important;
   }

   body {
      font-size:12pt;
      max-width:100%;
   }

   a, a:visited {
      text-decoration: underline;
   }

   hr {
      visibility: hidden;
      page-break-before: always;
   }

   pre, blockquote {
      padding-right: 1em;
      page-break-inside: avoid;
   }

   tr, img {
      page-break-inside: avoid;
   }

   img {
      max-width: 100% !important;
   }

   @page :left {
      margin: 15mm 20mm 15mm 10mm;
   }

   @page :right {
      margin: 15mm 10mm 15mm 20mm;
   }

   p, h2, h3 {
      orphans: 3; widows: 3;
   }

   h2, h3 {
      page-break-after: avoid;
   }
}
</style>




## Summary



First the variable is renamed to `res_rh`.


```r
res_rh = rh
```



The partition hierarchy and all available functions which can be applied to `res_rh` object.


```r
res_rh
```

```
#> A 'HierarchicalPartition' object with 4 combinations of top-value methods and partitioning methods.
#>   On a matrix with 375901 rows and 187 columns.
#>   Performed in total 47600 partitions.
#>   There are 23 groups under the following parameters:
#>     - min_samples: 6
#>     - mean_silhouette_cutoff: 0.9
#>     - min_n_signatures: 1000 (signatures are selected based on:)
#>       - fdr_cutoff: 0.05
#>       - group_diff: 0.25
#> 
#> Hierarchy of the partition:
#>   0, 187 cols
#>   |-- 01, 64 cols, 6134 signatures
#>   |   |-- 011, 22 cols, 720 signatures (c)
#>   |   |-- 012, 27 cols, 2904 signatures
#>   |   |   |-- 0121, 15 cols, 332 signatures (c)
#>   |   |   |-- 0122, 7 cols (b)
#>   |   |   `-- 0123, 5 cols (b)
#>   |   `-- 013, 15 cols, 1493 signatures
#>   |       |-- 0131, 6 cols (b)
#>   |       `-- 0132, 9 cols (b)
#>   |-- 02, 40 cols, 39918 signatures
#>   |   |-- 021, 8 cols (b)
#>   |   |-- 022, 19 cols, 8655 signatures
#>   |   |   |-- 0221, 8 cols (b)
#>   |   |   |-- 0222, 6 cols (b)
#>   |   |   `-- 0223, 5 cols (b)
#>   |   |-- 023, 5 cols (b)
#>   |   `-- 024, 8 cols (b)
#>   |-- 03, 49 cols, 6830 signatures
#>   |   |-- 031, 20 cols, 2176 signatures
#>   |   |   |-- 0311, 9 cols (b)
#>   |   |   |-- 0312, 6 cols (b)
#>   |   |   `-- 0313, 5 cols (b)
#>   |   |-- 032, 21 cols, 3323 signatures
#>   |   |   |-- 0321, 8 cols (b)
#>   |   |   |-- 0322, 9 cols (b)
#>   |   |   `-- 0323, 4 cols (b)
#>   |   `-- 033, 8 cols (b)
#>   `-- 04, 34 cols, 14245 signatures
#>       |-- 041, 17 cols, 2235 signatures
#>       |   |-- 0411, 8 cols (b)
#>       |   `-- 0412, 9 cols (b)
#>       |-- 042, 13 cols, 165 signatures (c)
#>       `-- 043, 4 cols (b)
#> Stop reason:
#>   b) Subgroup had too few columns.
#>   c) There were too few signatures.
#> 
#> Following methods can be applied to this 'HierarchicalPartition' object:
#>  [1] "all_leaves"            "all_nodes"             "cola_report"           "collect_classes"      
#>  [5] "colnames"              "compare_signatures"    "dimension_reduction"   "functional_enrichment"
#>  [9] "get_anno_col"          "get_anno"              "get_children_nodes"    "get_classes"          
#> [13] "get_matrix"            "get_signatures"        "is_leaf_node"          "max_depth"            
#> [17] "merge_node"            "ncol"                  "node_info"             "node_level"           
#> [21] "nrow"                  "rownames"              "show"                  "split_node"           
#> [25] "suggest_best_k"        "test_to_known_factors" "top_rows_heatmap"      "top_rows_overlap"     
#> 
#> You can get result for a single node by e.g. object["01"]
```

The call of `hierarchical_partition()` was:


```
#> hierarchical_partition(data = mat, top_n = 1000, top_value_method = c("SD", "ATC"), 
#>     partition_method = c("kmeans", "skmeans"), subset = 500, group_diff = 0.25, min_n_signatures = 1000, 
#>     filter_fun = function(mat) {
#>         s = rowSds(mat)
#>         order(-s)[1:30000]
#>     }, max_k = 8, scale_rows = FALSE, cores = 4)
```

Dimension of the input matrix:


```r
mat = get_matrix(res_rh)
dim(mat)
```

```
#> [1] 375901    187
```

All the methods that were tried:


```r
res_rh@param$combination_method
```

```
#> [[1]]
#> [1] "SD"     "kmeans"
#> 
#> [[2]]
#> [1] "ATC"    "kmeans"
#> 
#> [[3]]
#> [1] "SD"      "skmeans"
#> 
#> [[4]]
#> [1] "ATC"     "skmeans"
```

### Density distribution

The density distribution for each sample is visualized as one column in the following heatmap.
The clustering is based on the distance which is the Kolmogorov-Smirnov statistic between two distributions.




```r
library(ComplexHeatmap)
densityHeatmap(mat, ylab = "value", cluster_columns = TRUE, show_column_names = FALSE,
    mc.cores = 1)
```

![plot of chunk density-heatmap](figure_cola/density-heatmap-1.png)



Some values about the hierarchy:


```r
all_nodes(res_rh)
```

```
#>  [1] "0"    "01"   "011"  "012"  "0121" "0122" "0123" "013"  "0131" "0132" "02"   "021"  "022" 
#> [14] "0221" "0222" "0223" "023"  "024"  "03"   "031"  "0311" "0312" "0313" "032"  "0321" "0322"
#> [27] "0323" "033"  "04"   "041"  "0411" "0412" "042"  "043"
```

```r
all_leaves(res_rh)
```

```
#>  [1] "011"  "0121" "0122" "0123" "0131" "0132" "021"  "0221" "0222" "0223" "023"  "024"  "0311"
#> [14] "0312" "0313" "0321" "0322" "0323" "033"  "0411" "0412" "042"  "043"
```

```r
node_info(res_rh)
```

```
#>      id best_method depth best_k n_columns n_signatures p_signatures is_leaf
#> 1     0  ATC:kmeans     1      4       187        39337     0.104647   FALSE
#> 2    01  ATC:kmeans     2      3        64         6134     0.016318   FALSE
#> 3   011   SD:kmeans     3      3        22          720     0.001915    TRUE
#> 4   012 ATC:skmeans     3      3        27         2904     0.007725   FALSE
#> 5  0121  ATC:kmeans     4      2        15          332     0.000883    TRUE
#> 6  0122 not applied     4     NA         7           NA           NA    TRUE
#> 7  0123 not applied     4     NA         5           NA           NA    TRUE
#> 8   013 ATC:skmeans     3      2        15         1493     0.003972   FALSE
#> 9  0131 not applied     4     NA         6           NA           NA    TRUE
#> 10 0132 not applied     4     NA         9           NA           NA    TRUE
#> 11   02  SD:skmeans     2      4        40        39918     0.106193   FALSE
#> 12  021 not applied     3     NA         8           NA           NA    TRUE
#> 13  022  ATC:kmeans     3      3        19         8655     0.023025   FALSE
#> 14 0221 not applied     4     NA         8           NA           NA    TRUE
#> 15 0222 not applied     4     NA         6           NA           NA    TRUE
#> 16 0223 not applied     4     NA         5           NA           NA    TRUE
#> 17  023 not applied     3     NA         5           NA           NA    TRUE
#> 18  024 not applied     3     NA         8           NA           NA    TRUE
#> 19   03  ATC:kmeans     2      3        49         6830     0.018170   FALSE
#> 20  031 ATC:skmeans     3      3        20         2176     0.005789   FALSE
#> 21 0311 not applied     4     NA         9           NA           NA    TRUE
#> 22 0312 not applied     4     NA         6           NA           NA    TRUE
#> 23 0313 not applied     4     NA         5           NA           NA    TRUE
#> 24  032 ATC:skmeans     3      3        21         3323     0.008840   FALSE
#> 25 0321 not applied     4     NA         8           NA           NA    TRUE
#> 26 0322 not applied     4     NA         9           NA           NA    TRUE
#> 27 0323 not applied     4     NA         4           NA           NA    TRUE
#> 28  033 not applied     3     NA         8           NA           NA    TRUE
#> 29   04  ATC:kmeans     2      3        34        14245     0.037896   FALSE
#> 30  041  SD:skmeans     3      2        17         2235     0.005946   FALSE
#> 31 0411 not applied     4     NA         8           NA           NA    TRUE
#> 32 0412 not applied     4     NA         9           NA           NA    TRUE
#> 33  042  ATC:kmeans     3      2        13          165     0.000439    TRUE
#> 34  043 not applied     3     NA         4           NA           NA    TRUE
```

In the output from `node_info()`, there are the following columns:

- `id`: The node id.
- `best_method`: The best method selected.
- `depth`: Depth of the node in the hierarchy.
- `best_k`: Best number of groups of the partition on that node.
- `n_columns`: Number of columns in the submatrix.
- `n_signatures`: Number of signatures with the `best_k`.
- `p_signatures`: Proportion of hte signatures in total number of rows in the matrix.
- `is_leaf`: Whether the node is a leaf.

Labels of nodes are encoded in a special way. The number of digits
correspond to the depth of the node in the hierarchy and the value of the
digits correspond to the index of the subgroup in the current node, E.g. a label
of ???012??? means the node is the second subgroup of the partition which is the
first subgroup of the root node.

### Suggest the best k



Following table shows the best `k` (number of partitions) for each node in the
partition hierarchy. Clicking on the node name in the table goes to the
corresponding section for the partitioning on that node.

[The cola vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13)
explains the definition of the metrics used for determining the best
number of partitions.



```r
suggest_best_k(res_rh)
```


|Node                |Best method                                         |Is leaf   |Best k |1-PAC |Mean silhouette |Concordance | #samples|   |
|:-------------------|:---------------------------------------------------|:---------|:------|:-----|:---------------|:-----------|--------:|:--|
|[Node0](#Node0)     |ATC:kmeans                                          |          |4      |0.99  |0.96            |0.98        |      187|** |
|[Node01](#Node01)   |ATC:kmeans                                          |          |3      |1.00  |1.00            |1.00        |       64|** |
|Node011-leaf        |SD:kmeans                                           |??? (&#99;) |3      |1.00  |0.98            |0.98        |       22|** |
|[Node012](#Node012) |ATC:skmeans                                         |          |2      |1.00  |1.00            |1.00        |       27|** |
|Node0121-leaf       |ATC:kmeans                                          |??? (&#99;) |7      |0.95  |0.69            |0.95        |       15|** |
|Node0122-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        7|   |
|Node0123-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|[Node013](#Node013) |ATC:skmeans                                         |          |2      |1.00  |1.00            |1.00        |       15|** |
|Node0131-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        6|   |
|Node0132-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        9|   |
|[Node02](#Node02)   |SD:skmeans                                          |          |4      |1.00  |0.96            |0.99        |       40|** |
|Node021-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        8|   |
|[Node022](#Node022) |ATC:kmeans                                          |          |2      |1.00  |1.00            |1.00        |       19|** |
|Node0221-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        8|   |
|Node0222-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        6|   |
|Node0223-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|Node023-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|Node024-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        8|   |
|[Node03](#Node03)   |ATC:kmeans                                          |          |3      |1.00  |0.99            |1.00        |       49|** |
|[Node031](#Node031) |ATC:skmeans                                         |          |8      |0.95  |0.79            |0.94        |       20|*  |
|Node0311-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        9|   |
|Node0312-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        6|   |
|Node0313-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|[Node032](#Node032) |ATC:skmeans                                         |          |6      |0.91  |0.80            |0.93        |       21|*  |
|Node0321-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        8|   |
|Node0322-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        9|   |
|Node0323-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        4|   |
|Node033-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        8|   |
|[Node04](#Node04)   |ATC:kmeans                                          |          |3      |1.00  |0.98            |0.99        |       34|** |
|[Node041](#Node041) |SD:skmeans                                          |          |2      |1.00  |1.00            |1.00        |       17|** |
|Node0411-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        8|   |
|Node0412-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        9|   |
|Node042-leaf        |ATC:kmeans                                          |??? (&#99;) |2      |1.00  |1.00            |1.00        |       13|** |
|Node043-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        4|   |


Stop reason: b) Subgroup had too few columns. c) There were too few signatures. 

\*\*: 1-PAC > 0.95, \*: 1-PAC > 0.9


### Partition hierarchy

The nodes of the hierarchy can be merged by setting the `merge_node` parameters. Here we 
control the hierarchy with the `min_n_signatures` parameter. The value of `min_n_signatures` is
from `node_info()`.





<style type='text/css'>



.ui-helper-hidden {
	display: none;
}
.ui-helper-hidden-accessible {
	border: 0;
	clip: rect(0 0 0 0);
	height: 1px;
	margin: -1px;
	overflow: hidden;
	padding: 0;
	position: absolute;
	width: 1px;
}
.ui-helper-reset {
	margin: 0;
	padding: 0;
	border: 0;
	outline: 0;
	line-height: 1.3;
	text-decoration: none;
	font-size: 100%;
	list-style: none;
}
.ui-helper-clearfix:before,
.ui-helper-clearfix:after {
	content: "";
	display: table;
	border-collapse: collapse;
}
.ui-helper-clearfix:after {
	clear: both;
}
.ui-helper-zfix {
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	position: absolute;
	opacity: 0;
	filter:Alpha(Opacity=0); 
}

.ui-front {
	z-index: 100;
}



.ui-state-disabled {
	cursor: default !important;
	pointer-events: none;
}



.ui-icon {
	display: inline-block;
	vertical-align: middle;
	margin-top: -.25em;
	position: relative;
	text-indent: -99999px;
	overflow: hidden;
	background-repeat: no-repeat;
}

.ui-widget-icon-block {
	left: 50%;
	margin-left: -8px;
	display: block;
}




.ui-widget-overlay {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
.ui-accordion .ui-accordion-header {
	display: block;
	cursor: pointer;
	position: relative;
	margin: 2px 0 0 0;
	padding: .5em .5em .5em .7em;
	font-size: 100%;
}
.ui-accordion .ui-accordion-content {
	padding: 1em 2.2em;
	border-top: 0;
	overflow: auto;
}
.ui-autocomplete {
	position: absolute;
	top: 0;
	left: 0;
	cursor: default;
}
.ui-menu {
	list-style: none;
	padding: 0;
	margin: 0;
	display: block;
	outline: 0;
}
.ui-menu .ui-menu {
	position: absolute;
}
.ui-menu .ui-menu-item {
	margin: 0;
	cursor: pointer;
	
	list-style-image: url("data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7");
}
.ui-menu .ui-menu-item-wrapper {
	position: relative;
	padding: 3px 1em 3px .4em;
}
.ui-menu .ui-menu-divider {
	margin: 5px 0;
	height: 0;
	font-size: 0;
	line-height: 0;
	border-width: 1px 0 0 0;
}
.ui-menu .ui-state-focus,
.ui-menu .ui-state-active {
	margin: -1px;
}


.ui-menu-icons {
	position: relative;
}
.ui-menu-icons .ui-menu-item-wrapper {
	padding-left: 2em;
}


.ui-menu .ui-icon {
	position: absolute;
	top: 0;
	bottom: 0;
	left: .2em;
	margin: auto 0;
}


.ui-menu .ui-menu-icon {
	left: auto;
	right: 0;
}
.ui-button {
	padding: .4em 1em;
	display: inline-block;
	position: relative;
	line-height: normal;
	margin-right: .1em;
	cursor: pointer;
	vertical-align: middle;
	text-align: center;
	-webkit-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;
	user-select: none;

	
	overflow: visible;
}

.ui-button,
.ui-button:link,
.ui-button:visited,
.ui-button:hover,
.ui-button:active {
	text-decoration: none;
}


.ui-button-icon-only {
	width: 2em;
	box-sizing: border-box;
	text-indent: -9999px;
	white-space: nowrap;
}


input.ui-button.ui-button-icon-only {
	text-indent: 0;
}


.ui-button-icon-only .ui-icon {
	position: absolute;
	top: 50%;
	left: 50%;
	margin-top: -8px;
	margin-left: -8px;
}

.ui-button.ui-icon-notext .ui-icon {
	padding: 0;
	width: 2.1em;
	height: 2.1em;
	text-indent: -9999px;
	white-space: nowrap;

}

input.ui-button.ui-icon-notext .ui-icon {
	width: auto;
	height: auto;
	text-indent: 0;
	white-space: normal;
	padding: .4em 1em;
}



input.ui-button::-moz-focus-inner,
button.ui-button::-moz-focus-inner {
	border: 0;
	padding: 0;
}
.ui-controlgroup {
	vertical-align: middle;
	display: inline-block;
}
.ui-controlgroup > .ui-controlgroup-item {
	float: left;
	margin-left: 0;
	margin-right: 0;
}
.ui-controlgroup > .ui-controlgroup-item:focus,
.ui-controlgroup > .ui-controlgroup-item.ui-visual-focus {
	z-index: 9999;
}
.ui-controlgroup-vertical > .ui-controlgroup-item {
	display: block;
	float: none;
	width: 100%;
	margin-top: 0;
	margin-bottom: 0;
	text-align: left;
}
.ui-controlgroup-vertical .ui-controlgroup-item {
	box-sizing: border-box;
}
.ui-controlgroup .ui-controlgroup-label {
	padding: .4em 1em;
}
.ui-controlgroup .ui-controlgroup-label span {
	font-size: 80%;
}
.ui-controlgroup-horizontal .ui-controlgroup-label + .ui-controlgroup-item {
	border-left: none;
}
.ui-controlgroup-vertical .ui-controlgroup-label + .ui-controlgroup-item {
	border-top: none;
}
.ui-controlgroup-horizontal .ui-controlgroup-label.ui-widget-content {
	border-right: none;
}
.ui-controlgroup-vertical .ui-controlgroup-label.ui-widget-content {
	border-bottom: none;
}


.ui-controlgroup-vertical .ui-spinner-input {

	
	width: 75%;
	width: calc( 100% - 2.4em );
}
.ui-controlgroup-vertical .ui-spinner .ui-spinner-up {
	border-top-style: solid;
}

.ui-checkboxradio-label .ui-icon-background {
	box-shadow: inset 1px 1px 1px #ccc;
	border-radius: .12em;
	border: none;
}
.ui-checkboxradio-radio-label .ui-icon-background {
	width: 16px;
	height: 16px;
	border-radius: 1em;
	overflow: visible;
	border: none;
}
.ui-checkboxradio-radio-label.ui-checkboxradio-checked .ui-icon,
.ui-checkboxradio-radio-label.ui-checkboxradio-checked:hover .ui-icon {
	background-image: none;
	width: 8px;
	height: 8px;
	border-width: 4px;
	border-style: solid;
}
.ui-checkboxradio-disabled {
	pointer-events: none;
}
.ui-datepicker {
	width: 17em;
	padding: .2em .2em 0;
	display: none;
}
.ui-datepicker .ui-datepicker-header {
	position: relative;
	padding: .2em 0;
}
.ui-datepicker .ui-datepicker-prev,
.ui-datepicker .ui-datepicker-next {
	position: absolute;
	top: 2px;
	width: 1.8em;
	height: 1.8em;
}
.ui-datepicker .ui-datepicker-prev-hover,
.ui-datepicker .ui-datepicker-next-hover {
	top: 1px;
}
.ui-datepicker .ui-datepicker-prev {
	left: 2px;
}
.ui-datepicker .ui-datepicker-next {
	right: 2px;
}
.ui-datepicker .ui-datepicker-prev-hover {
	left: 1px;
}
.ui-datepicker .ui-datepicker-next-hover {
	right: 1px;
}
.ui-datepicker .ui-datepicker-prev span,
.ui-datepicker .ui-datepicker-next span {
	display: block;
	position: absolute;
	left: 50%;
	margin-left: -8px;
	top: 50%;
	margin-top: -8px;
}
.ui-datepicker .ui-datepicker-title {
	margin: 0 2.3em;
	line-height: 1.8em;
	text-align: center;
}
.ui-datepicker .ui-datepicker-title select {
	font-size: 1em;
	margin: 1px 0;
}
.ui-datepicker select.ui-datepicker-month,
.ui-datepicker select.ui-datepicker-year {
	width: 45%;
}
.ui-datepicker table {
	width: 100%;
	font-size: .9em;
	border-collapse: collapse;
	margin: 0 0 .4em;
}
.ui-datepicker th {
	padding: .7em .3em;
	text-align: center;
	font-weight: bold;
	border: 0;
}
.ui-datepicker td {
	border: 0;
	padding: 1px;
}
.ui-datepicker td span,
.ui-datepicker td a {
	display: block;
	padding: .2em;
	text-align: right;
	text-decoration: none;
}
.ui-datepicker .ui-datepicker-buttonpane {
	background-image: none;
	margin: .7em 0 0 0;
	padding: 0 .2em;
	border-left: 0;
	border-right: 0;
	border-bottom: 0;
}
.ui-datepicker .ui-datepicker-buttonpane button {
	float: right;
	margin: .5em .2em .4em;
	cursor: pointer;
	padding: .2em .6em .3em .6em;
	width: auto;
	overflow: visible;
}
.ui-datepicker .ui-datepicker-buttonpane button.ui-datepicker-current {
	float: left;
}


.ui-datepicker.ui-datepicker-multi {
	width: auto;
}
.ui-datepicker-multi .ui-datepicker-group {
	float: left;
}
.ui-datepicker-multi .ui-datepicker-group table {
	width: 95%;
	margin: 0 auto .4em;
}
.ui-datepicker-multi-2 .ui-datepicker-group {
	width: 50%;
}
.ui-datepicker-multi-3 .ui-datepicker-group {
	width: 33.3%;
}
.ui-datepicker-multi-4 .ui-datepicker-group {
	width: 25%;
}
.ui-datepicker-multi .ui-datepicker-group-last .ui-datepicker-header,
.ui-datepicker-multi .ui-datepicker-group-middle .ui-datepicker-header {
	border-left-width: 0;
}
.ui-datepicker-multi .ui-datepicker-buttonpane {
	clear: left;
}
.ui-datepicker-row-break {
	clear: both;
	width: 100%;
	font-size: 0;
}


.ui-datepicker-rtl {
	direction: rtl;
}
.ui-datepicker-rtl .ui-datepicker-prev {
	right: 2px;
	left: auto;
}
.ui-datepicker-rtl .ui-datepicker-next {
	left: 2px;
	right: auto;
}
.ui-datepicker-rtl .ui-datepicker-prev:hover {
	right: 1px;
	left: auto;
}
.ui-datepicker-rtl .ui-datepicker-next:hover {
	left: 1px;
	right: auto;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane {
	clear: right;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane button {
	float: left;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane button.ui-datepicker-current,
.ui-datepicker-rtl .ui-datepicker-group {
	float: right;
}
.ui-datepicker-rtl .ui-datepicker-group-last .ui-datepicker-header,
.ui-datepicker-rtl .ui-datepicker-group-middle .ui-datepicker-header {
	border-right-width: 0;
	border-left-width: 1px;
}


.ui-datepicker .ui-icon {
	display: block;
	text-indent: -99999px;
	overflow: hidden;
	background-repeat: no-repeat;
	left: .5em;
	top: .3em;
}
.ui-dialog {
	position: absolute;
	top: 0;
	left: 0;
	padding: .2em;
	outline: 0;
}
.ui-dialog .ui-dialog-titlebar {
	padding: .4em 1em;
	position: relative;
}
.ui-dialog .ui-dialog-title {
	float: left;
	margin: .1em 0;
	white-space: nowrap;
	width: 90%;
	overflow: hidden;
	text-overflow: ellipsis;
}
.ui-dialog .ui-dialog-titlebar-close {
	position: absolute;
	right: .3em;
	top: 50%;
	width: 20px;
	margin: -10px 0 0 0;
	padding: 1px;
	height: 20px;
}
.ui-dialog .ui-dialog-content {
	position: relative;
	border: 0;
	padding: .5em 1em;
	background: none;
	overflow: auto;
}
.ui-dialog .ui-dialog-buttonpane {
	text-align: left;
	border-width: 1px 0 0 0;
	background-image: none;
	margin-top: .5em;
	padding: .3em 1em .5em .4em;
}
.ui-dialog .ui-dialog-buttonpane .ui-dialog-buttonset {
	float: right;
}
.ui-dialog .ui-dialog-buttonpane button {
	margin: .5em .4em .5em 0;
	cursor: pointer;
}
.ui-dialog .ui-resizable-n {
	height: 2px;
	top: 0;
}
.ui-dialog .ui-resizable-e {
	width: 2px;
	right: 0;
}
.ui-dialog .ui-resizable-s {
	height: 2px;
	bottom: 0;
}
.ui-dialog .ui-resizable-w {
	width: 2px;
	left: 0;
}
.ui-dialog .ui-resizable-se,
.ui-dialog .ui-resizable-sw,
.ui-dialog .ui-resizable-ne,
.ui-dialog .ui-resizable-nw {
	width: 7px;
	height: 7px;
}
.ui-dialog .ui-resizable-se {
	right: 0;
	bottom: 0;
}
.ui-dialog .ui-resizable-sw {
	left: 0;
	bottom: 0;
}
.ui-dialog .ui-resizable-ne {
	right: 0;
	top: 0;
}
.ui-dialog .ui-resizable-nw {
	left: 0;
	top: 0;
}
.ui-draggable .ui-dialog-titlebar {
	cursor: move;
}
.ui-draggable-handle {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-resizable {
	position: relative;
}
.ui-resizable-handle {
	position: absolute;
	font-size: 0.1px;
	display: block;
	-ms-touch-action: none;
	touch-action: none;
}
.ui-resizable-disabled .ui-resizable-handle,
.ui-resizable-autohide .ui-resizable-handle {
	display: none;
}
.ui-resizable-n {
	cursor: n-resize;
	height: 7px;
	width: 100%;
	top: -5px;
	left: 0;
}
.ui-resizable-s {
	cursor: s-resize;
	height: 7px;
	width: 100%;
	bottom: -5px;
	left: 0;
}
.ui-resizable-e {
	cursor: e-resize;
	width: 7px;
	right: -5px;
	top: 0;
	height: 100%;
}
.ui-resizable-w {
	cursor: w-resize;
	width: 7px;
	left: -5px;
	top: 0;
	height: 100%;
}
.ui-resizable-se {
	cursor: se-resize;
	width: 12px;
	height: 12px;
	right: 1px;
	bottom: 1px;
}
.ui-resizable-sw {
	cursor: sw-resize;
	width: 9px;
	height: 9px;
	left: -5px;
	bottom: -5px;
}
.ui-resizable-nw {
	cursor: nw-resize;
	width: 9px;
	height: 9px;
	left: -5px;
	top: -5px;
}
.ui-resizable-ne {
	cursor: ne-resize;
	width: 9px;
	height: 9px;
	right: -5px;
	top: -5px;
}
.ui-progressbar {
	height: 2em;
	text-align: left;
	overflow: hidden;
}
.ui-progressbar .ui-progressbar-value {
	margin: -1px;
	height: 100%;
}
.ui-progressbar .ui-progressbar-overlay {
	background: url("data:image/gif;base64,R0lGODlhKAAoAIABAAAAAP///yH/C05FVFNDQVBFMi4wAwEAAAAh+QQJAQABACwAAAAAKAAoAAACkYwNqXrdC52DS06a7MFZI+4FHBCKoDeWKXqymPqGqxvJrXZbMx7Ttc+w9XgU2FB3lOyQRWET2IFGiU9m1frDVpxZZc6bfHwv4c1YXP6k1Vdy292Fb6UkuvFtXpvWSzA+HycXJHUXiGYIiMg2R6W459gnWGfHNdjIqDWVqemH2ekpObkpOlppWUqZiqr6edqqWQAAIfkECQEAAQAsAAAAACgAKAAAApSMgZnGfaqcg1E2uuzDmmHUBR8Qil95hiPKqWn3aqtLsS18y7G1SzNeowWBENtQd+T1JktP05nzPTdJZlR6vUxNWWjV+vUWhWNkWFwxl9VpZRedYcflIOLafaa28XdsH/ynlcc1uPVDZxQIR0K25+cICCmoqCe5mGhZOfeYSUh5yJcJyrkZWWpaR8doJ2o4NYq62lAAACH5BAkBAAEALAAAAAAoACgAAAKVDI4Yy22ZnINRNqosw0Bv7i1gyHUkFj7oSaWlu3ovC8GxNso5fluz3qLVhBVeT/Lz7ZTHyxL5dDalQWPVOsQWtRnuwXaFTj9jVVh8pma9JjZ4zYSj5ZOyma7uuolffh+IR5aW97cHuBUXKGKXlKjn+DiHWMcYJah4N0lYCMlJOXipGRr5qdgoSTrqWSq6WFl2ypoaUAAAIfkECQEAAQAsAAAAACgAKAAAApaEb6HLgd/iO7FNWtcFWe+ufODGjRfoiJ2akShbueb0wtI50zm02pbvwfWEMWBQ1zKGlLIhskiEPm9R6vRXxV4ZzWT2yHOGpWMyorblKlNp8HmHEb/lCXjcW7bmtXP8Xt229OVWR1fod2eWqNfHuMjXCPkIGNileOiImVmCOEmoSfn3yXlJWmoHGhqp6ilYuWYpmTqKUgAAIfkECQEAAQAsAAAAACgAKAAAApiEH6kb58biQ3FNWtMFWW3eNVcojuFGfqnZqSebuS06w5V80/X02pKe8zFwP6EFWOT1lDFk8rGERh1TTNOocQ61Hm4Xm2VexUHpzjymViHrFbiELsefVrn6XKfnt2Q9G/+Xdie499XHd2g4h7ioOGhXGJboGAnXSBnoBwKYyfioubZJ2Hn0RuRZaflZOil56Zp6iioKSXpUAAAh+QQJAQABACwAAAAAKAAoAAACkoQRqRvnxuI7kU1a1UU5bd5tnSeOZXhmn5lWK3qNTWvRdQxP8qvaC+/yaYQzXO7BMvaUEmJRd3TsiMAgswmNYrSgZdYrTX6tSHGZO73ezuAw2uxuQ+BbeZfMxsexY35+/Qe4J1inV0g4x3WHuMhIl2jXOKT2Q+VU5fgoSUI52VfZyfkJGkha6jmY+aaYdirq+lQAACH5BAkBAAEALAAAAAAoACgAAAKWBIKpYe0L3YNKToqswUlvznigd4wiR4KhZrKt9Upqip61i9E3vMvxRdHlbEFiEXfk9YARYxOZZD6VQ2pUunBmtRXo1Lf8hMVVcNl8JafV38aM2/Fu5V16Bn63r6xt97j09+MXSFi4BniGFae3hzbH9+hYBzkpuUh5aZmHuanZOZgIuvbGiNeomCnaxxap2upaCZsq+1kAACH5BAkBAAEALAAAAAAoACgAAAKXjI8By5zf4kOxTVrXNVlv1X0d8IGZGKLnNpYtm8Lr9cqVeuOSvfOW79D9aDHizNhDJidFZhNydEahOaDH6nomtJjp1tutKoNWkvA6JqfRVLHU/QUfau9l2x7G54d1fl995xcIGAdXqMfBNadoYrhH+Mg2KBlpVpbluCiXmMnZ2Sh4GBqJ+ckIOqqJ6LmKSllZmsoq6wpQAAAh+QQJAQABACwAAAAAKAAoAAAClYx/oLvoxuJDkU1a1YUZbJ59nSd2ZXhWqbRa2/gF8Gu2DY3iqs7yrq+xBYEkYvFSM8aSSObE+ZgRl1BHFZNr7pRCavZ5BW2142hY3AN/zWtsmf12p9XxxFl2lpLn1rseztfXZjdIWIf2s5dItwjYKBgo9yg5pHgzJXTEeGlZuenpyPmpGQoKOWkYmSpaSnqKileI2FAAACH5BAkBAAEALAAAAAAoACgAAAKVjB+gu+jG4kORTVrVhRlsnn2dJ3ZleFaptFrb+CXmO9OozeL5VfP99HvAWhpiUdcwkpBH3825AwYdU8xTqlLGhtCosArKMpvfa1mMRae9VvWZfeB2XfPkeLmm18lUcBj+p5dnN8jXZ3YIGEhYuOUn45aoCDkp16hl5IjYJvjWKcnoGQpqyPlpOhr3aElaqrq56Bq7VAAAOw==");
	height: 100%;
	filter: alpha(opacity=25); 
	opacity: 0.25;
}
.ui-progressbar-indeterminate .ui-progressbar-value {
	background-image: none;
}
.ui-selectable {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-selectable-helper {
	position: absolute;
	z-index: 100;
	border: 1px dotted black;
}
.ui-selectmenu-menu {
	padding: 0;
	margin: 0;
	position: absolute;
	top: 0;
	left: 0;
	display: none;
}
.ui-selectmenu-menu .ui-menu {
	overflow: auto;
	overflow-x: hidden;
	padding-bottom: 1px;
}
.ui-selectmenu-menu .ui-menu .ui-selectmenu-optgroup {
	font-size: 1em;
	font-weight: bold;
	line-height: 1.5;
	padding: 2px 0.4em;
	margin: 0.5em 0 0 0;
	height: auto;
	border: 0;
}
.ui-selectmenu-open {
	display: block;
}
.ui-selectmenu-text {
	display: block;
	margin-right: 20px;
	overflow: hidden;
	text-overflow: ellipsis;
}
.ui-selectmenu-button.ui-button {
	text-align: left;
	white-space: nowrap;
	width: 14em;
}
.ui-selectmenu-icon.ui-icon {
	float: right;
	margin-top: 0;
}
.ui-slider {
	position: relative;
	text-align: left;
}
.ui-slider .ui-slider-handle {
	position: absolute;
	z-index: 2;
	width: 1.2em;
	height: 1.2em;
	cursor: default;
	-ms-touch-action: none;
	touch-action: none;
}
.ui-slider .ui-slider-range {
	position: absolute;
	z-index: 1;
	font-size: .7em;
	display: block;
	border: 0;
	background-position: 0 0;
}


.ui-slider.ui-state-disabled .ui-slider-handle,
.ui-slider.ui-state-disabled .ui-slider-range {
	filter: inherit;
}

.ui-slider-horizontal {
	height: .8em;
}
.ui-slider-horizontal .ui-slider-handle {
	top: -.3em;
	margin-left: -.6em;
}
.ui-slider-horizontal .ui-slider-range {
	top: 0;
	height: 100%;
}
.ui-slider-horizontal .ui-slider-range-min {
	left: 0;
}
.ui-slider-horizontal .ui-slider-range-max {
	right: 0;
}

.ui-slider-vertical {
	width: .8em;
	height: 100px;
}
.ui-slider-vertical .ui-slider-handle {
	left: -.3em;
	margin-left: 0;
	margin-bottom: -.6em;
}
.ui-slider-vertical .ui-slider-range {
	left: 0;
	width: 100%;
}
.ui-slider-vertical .ui-slider-range-min {
	bottom: 0;
}
.ui-slider-vertical .ui-slider-range-max {
	top: 0;
}
.ui-sortable-handle {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-spinner {
	position: relative;
	display: inline-block;
	overflow: hidden;
	padding: 0;
	vertical-align: middle;
}
.ui-spinner-input {
	border: none;
	background: none;
	color: inherit;
	padding: .222em 0;
	margin: .2em 0;
	vertical-align: middle;
	margin-left: .4em;
	margin-right: 2em;
}
.ui-spinner-button {
	width: 1.6em;
	height: 50%;
	font-size: .5em;
	padding: 0;
	margin: 0;
	text-align: center;
	position: absolute;
	cursor: default;
	display: block;
	overflow: hidden;
	right: 0;
}

.ui-spinner a.ui-spinner-button {
	border-top-style: none;
	border-bottom-style: none;
	border-right-style: none;
}
.ui-spinner-up {
	top: 0;
}
.ui-spinner-down {
	bottom: 0;
}
.ui-tabs {
	position: relative;
	padding: .2em;
}
.ui-tabs .ui-tabs-nav {
	margin: 0;
	padding: .2em .2em 0;
}
.ui-tabs .ui-tabs-nav li {
	list-style: none;
	float: left;
	position: relative;
	top: 0;
	margin: 1px .2em 0 0;
	border-bottom-width: 0;
	padding: 0;
	white-space: nowrap;
}
.ui-tabs .ui-tabs-nav .ui-tabs-anchor {
	float: left;
	padding: .5em 1em;
	text-decoration: none;
}
.ui-tabs .ui-tabs-nav li.ui-tabs-active {
	margin-bottom: -1px;
	padding-bottom: 1px;
}
.ui-tabs .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor,
.ui-tabs .ui-tabs-nav li.ui-state-disabled .ui-tabs-anchor,
.ui-tabs .ui-tabs-nav li.ui-tabs-loading .ui-tabs-anchor {
	cursor: text;
}
.ui-tabs-collapsible .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor {
	cursor: pointer;
}
.ui-tabs .ui-tabs-panel {
	display: block;
	border-width: 0;
	padding: 1em 1.4em;
	background: none;
}
.ui-tooltip {
	padding: 8px;
	position: absolute;
	z-index: 9999;
	max-width: 300px;
}
body .ui-tooltip {
	border-width: 2px;
}

.ui-widget {
	font-family: Arial,Helvetica,sans-serif;
	font-size: 1em;
}
.ui-widget .ui-widget {
	font-size: 1em;
}
.ui-widget input,
.ui-widget select,
.ui-widget textarea,
.ui-widget button {
	font-family: Arial,Helvetica,sans-serif;
	font-size: 1em;
}
.ui-widget.ui-widget-content {
	border: 1px solid #c5c5c5;
}
.ui-widget-content {
	border: 1px solid #dddddd;
	background: #ffffff;
	color: #333333;
}
.ui-widget-content a {
	color: #333333;
}
.ui-widget-header {
	border: 1px solid #dddddd;
	background: #e9e9e9;
	color: #333333;
	font-weight: bold;
}
.ui-widget-header a {
	color: #333333;
}


.ui-state-default,
.ui-widget-content .ui-state-default,
.ui-widget-header .ui-state-default,
.ui-button,


html .ui-button.ui-state-disabled:hover,
html .ui-button.ui-state-disabled:active {
	border: 1px solid #c5c5c5;
	background: #f6f6f6;
	font-weight: normal;
	color: #454545;
}
.ui-state-default a,
.ui-state-default a:link,
.ui-state-default a:visited,
a.ui-button,
a:link.ui-button,
a:visited.ui-button,
.ui-button {
	color: #454545;
	text-decoration: none;
}
.ui-state-hover,
.ui-widget-content .ui-state-hover,
.ui-widget-header .ui-state-hover,
.ui-state-focus,
.ui-widget-content .ui-state-focus,
.ui-widget-header .ui-state-focus,
.ui-button:hover,
.ui-button:focus {
	border: 1px solid #cccccc;
	background: #ededed;
	font-weight: normal;
	color: #2b2b2b;
}
.ui-state-hover a,
.ui-state-hover a:hover,
.ui-state-hover a:link,
.ui-state-hover a:visited,
.ui-state-focus a,
.ui-state-focus a:hover,
.ui-state-focus a:link,
.ui-state-focus a:visited,
a.ui-button:hover,
a.ui-button:focus {
	color: #2b2b2b;
	text-decoration: none;
}

.ui-visual-focus {
	box-shadow: 0 0 3px 1px rgb(94, 158, 214);
}
.ui-state-active,
.ui-widget-content .ui-state-active,
.ui-widget-header .ui-state-active,
a.ui-button:active,
.ui-button:active,
.ui-button.ui-state-active:hover {
	border: 1px solid #003eff;
	background: #007fff;
	font-weight: normal;
	color: #ffffff;
}
.ui-icon-background,
.ui-state-active .ui-icon-background {
	border: #003eff;
	background-color: #ffffff;
}
.ui-state-active a,
.ui-state-active a:link,
.ui-state-active a:visited {
	color: #ffffff;
	text-decoration: none;
}


.ui-state-highlight,
.ui-widget-content .ui-state-highlight,
.ui-widget-header .ui-state-highlight {
	border: 1px solid #dad55e;
	background: #fffa90;
	color: #777620;
}
.ui-state-checked {
	border: 1px solid #dad55e;
	background: #fffa90;
}
.ui-state-highlight a,
.ui-widget-content .ui-state-highlight a,
.ui-widget-header .ui-state-highlight a {
	color: #777620;
}
.ui-state-error,
.ui-widget-content .ui-state-error,
.ui-widget-header .ui-state-error {
	border: 1px solid #f1a899;
	background: #fddfdf;
	color: #5f3f3f;
}
.ui-state-error a,
.ui-widget-content .ui-state-error a,
.ui-widget-header .ui-state-error a {
	color: #5f3f3f;
}
.ui-state-error-text,
.ui-widget-content .ui-state-error-text,
.ui-widget-header .ui-state-error-text {
	color: #5f3f3f;
}
.ui-priority-primary,
.ui-widget-content .ui-priority-primary,
.ui-widget-header .ui-priority-primary {
	font-weight: bold;
}
.ui-priority-secondary,
.ui-widget-content .ui-priority-secondary,
.ui-widget-header .ui-priority-secondary {
	opacity: .7;
	filter:Alpha(Opacity=70); 
	font-weight: normal;
}
.ui-state-disabled,
.ui-widget-content .ui-state-disabled,
.ui-widget-header .ui-state-disabled {
	opacity: .35;
	filter:Alpha(Opacity=35); 
	background-image: none;
}
.ui-state-disabled .ui-icon {
	filter:Alpha(Opacity=35); 
}




.ui-icon {
	width: 16px;
	height: 16px;
}
.ui-icon,
.ui-widget-content .ui-icon {
	background-image: url("images/ui-icons_444444_256x240.png");
}
.ui-widget-header .ui-icon {
	background-image: url("images/ui-icons_444444_256x240.png");
}
.ui-state-hover .ui-icon,
.ui-state-focus .ui-icon,
.ui-button:hover .ui-icon,
.ui-button:focus .ui-icon {
	background-image: url("images/ui-icons_555555_256x240.png");
}
.ui-state-active .ui-icon,
.ui-button:active .ui-icon {
	background-image: url("images/ui-icons_ffffff_256x240.png");
}
.ui-state-highlight .ui-icon,
.ui-button .ui-state-highlight.ui-icon {
	background-image: url("images/ui-icons_777620_256x240.png");
}
.ui-state-error .ui-icon,
.ui-state-error-text .ui-icon {
	background-image: url("images/ui-icons_cc0000_256x240.png");
}
.ui-button .ui-icon {
	background-image: url("images/ui-icons_777777_256x240.png");
}


.ui-icon-blank { background-position: 16px 16px; }
.ui-icon-caret-1-n { background-position: 0 0; }
.ui-icon-caret-1-ne { background-position: -16px 0; }
.ui-icon-caret-1-e { background-position: -32px 0; }
.ui-icon-caret-1-se { background-position: -48px 0; }
.ui-icon-caret-1-s { background-position: -65px 0; }
.ui-icon-caret-1-sw { background-position: -80px 0; }
.ui-icon-caret-1-w { background-position: -96px 0; }
.ui-icon-caret-1-nw { background-position: -112px 0; }
.ui-icon-caret-2-n-s { background-position: -128px 0; }
.ui-icon-caret-2-e-w { background-position: -144px 0; }
.ui-icon-triangle-1-n { background-position: 0 -16px; }
.ui-icon-triangle-1-ne { background-position: -16px -16px; }
.ui-icon-triangle-1-e { background-position: -32px -16px; }
.ui-icon-triangle-1-se { background-position: -48px -16px; }
.ui-icon-triangle-1-s { background-position: -65px -16px; }
.ui-icon-triangle-1-sw { background-position: -80px -16px; }
.ui-icon-triangle-1-w { background-position: -96px -16px; }
.ui-icon-triangle-1-nw { background-position: -112px -16px; }
.ui-icon-triangle-2-n-s { background-position: -128px -16px; }
.ui-icon-triangle-2-e-w { background-position: -144px -16px; }
.ui-icon-arrow-1-n { background-position: 0 -32px; }
.ui-icon-arrow-1-ne { background-position: -16px -32px; }
.ui-icon-arrow-1-e { background-position: -32px -32px; }
.ui-icon-arrow-1-se { background-position: -48px -32px; }
.ui-icon-arrow-1-s { background-position: -65px -32px; }
.ui-icon-arrow-1-sw { background-position: -80px -32px; }
.ui-icon-arrow-1-w { background-position: -96px -32px; }
.ui-icon-arrow-1-nw { background-position: -112px -32px; }
.ui-icon-arrow-2-n-s { background-position: -128px -32px; }
.ui-icon-arrow-2-ne-sw { background-position: -144px -32px; }
.ui-icon-arrow-2-e-w { background-position: -160px -32px; }
.ui-icon-arrow-2-se-nw { background-position: -176px -32px; }
.ui-icon-arrowstop-1-n { background-position: -192px -32px; }
.ui-icon-arrowstop-1-e { background-position: -208px -32px; }
.ui-icon-arrowstop-1-s { background-position: -224px -32px; }
.ui-icon-arrowstop-1-w { background-position: -240px -32px; }
.ui-icon-arrowthick-1-n { background-position: 1px -48px; }
.ui-icon-arrowthick-1-ne { background-position: -16px -48px; }
.ui-icon-arrowthick-1-e { background-position: -32px -48px; }
.ui-icon-arrowthick-1-se { background-position: -48px -48px; }
.ui-icon-arrowthick-1-s { background-position: -64px -48px; }
.ui-icon-arrowthick-1-sw { background-position: -80px -48px; }
.ui-icon-arrowthick-1-w { background-position: -96px -48px; }
.ui-icon-arrowthick-1-nw { background-position: -112px -48px; }
.ui-icon-arrowthick-2-n-s { background-position: -128px -48px; }
.ui-icon-arrowthick-2-ne-sw { background-position: -144px -48px; }
.ui-icon-arrowthick-2-e-w { background-position: -160px -48px; }
.ui-icon-arrowthick-2-se-nw { background-position: -176px -48px; }
.ui-icon-arrowthickstop-1-n { background-position: -192px -48px; }
.ui-icon-arrowthickstop-1-e { background-position: -208px -48px; }
.ui-icon-arrowthickstop-1-s { background-position: -224px -48px; }
.ui-icon-arrowthickstop-1-w { background-position: -240px -48px; }
.ui-icon-arrowreturnthick-1-w { background-position: 0 -64px; }
.ui-icon-arrowreturnthick-1-n { background-position: -16px -64px; }
.ui-icon-arrowreturnthick-1-e { background-position: -32px -64px; }
.ui-icon-arrowreturnthick-1-s { background-position: -48px -64px; }
.ui-icon-arrowreturn-1-w { background-position: -64px -64px; }
.ui-icon-arrowreturn-1-n { background-position: -80px -64px; }
.ui-icon-arrowreturn-1-e { background-position: -96px -64px; }
.ui-icon-arrowreturn-1-s { background-position: -112px -64px; }
.ui-icon-arrowrefresh-1-w { background-position: -128px -64px; }
.ui-icon-arrowrefresh-1-n { background-position: -144px -64px; }
.ui-icon-arrowrefresh-1-e { background-position: -160px -64px; }
.ui-icon-arrowrefresh-1-s { background-position: -176px -64px; }
.ui-icon-arrow-4 { background-position: 0 -80px; }
.ui-icon-arrow-4-diag { background-position: -16px -80px; }
.ui-icon-extlink { background-position: -32px -80px; }
.ui-icon-newwin { background-position: -48px -80px; }
.ui-icon-refresh { background-position: -64px -80px; }
.ui-icon-shuffle { background-position: -80px -80px; }
.ui-icon-transfer-e-w { background-position: -96px -80px; }
.ui-icon-transferthick-e-w { background-position: -112px -80px; }
.ui-icon-folder-collapsed { background-position: 0 -96px; }
.ui-icon-folder-open { background-position: -16px -96px; }
.ui-icon-document { background-position: -32px -96px; }
.ui-icon-document-b { background-position: -48px -96px; }
.ui-icon-note { background-position: -64px -96px; }
.ui-icon-mail-closed { background-position: -80px -96px; }
.ui-icon-mail-open { background-position: -96px -96px; }
.ui-icon-suitcase { background-position: -112px -96px; }
.ui-icon-comment { background-position: -128px -96px; }
.ui-icon-person { background-position: -144px -96px; }
.ui-icon-print { background-position: -160px -96px; }
.ui-icon-trash { background-position: -176px -96px; }
.ui-icon-locked { background-position: -192px -96px; }
.ui-icon-unlocked { background-position: -208px -96px; }
.ui-icon-bookmark { background-position: -224px -96px; }
.ui-icon-tag { background-position: -240px -96px; }
.ui-icon-home { background-position: 0 -112px; }
.ui-icon-flag { background-position: -16px -112px; }
.ui-icon-calendar { background-position: -32px -112px; }
.ui-icon-cart { background-position: -48px -112px; }
.ui-icon-pencil { background-position: -64px -112px; }
.ui-icon-clock { background-position: -80px -112px; }
.ui-icon-disk { background-position: -96px -112px; }
.ui-icon-calculator { background-position: -112px -112px; }
.ui-icon-zoomin { background-position: -128px -112px; }
.ui-icon-zoomout { background-position: -144px -112px; }
.ui-icon-search { background-position: -160px -112px; }
.ui-icon-wrench { background-position: -176px -112px; }
.ui-icon-gear { background-position: -192px -112px; }
.ui-icon-heart { background-position: -208px -112px; }
.ui-icon-star { background-position: -224px -112px; }
.ui-icon-link { background-position: -240px -112px; }
.ui-icon-cancel { background-position: 0 -128px; }
.ui-icon-plus { background-position: -16px -128px; }
.ui-icon-plusthick { background-position: -32px -128px; }
.ui-icon-minus { background-position: -48px -128px; }
.ui-icon-minusthick { background-position: -64px -128px; }
.ui-icon-close { background-position: -80px -128px; }
.ui-icon-closethick { background-position: -96px -128px; }
.ui-icon-key { background-position: -112px -128px; }
.ui-icon-lightbulb { background-position: -128px -128px; }
.ui-icon-scissors { background-position: -144px -128px; }
.ui-icon-clipboard { background-position: -160px -128px; }
.ui-icon-copy { background-position: -176px -128px; }
.ui-icon-contact { background-position: -192px -128px; }
.ui-icon-image { background-position: -208px -128px; }
.ui-icon-video { background-position: -224px -128px; }
.ui-icon-script { background-position: -240px -128px; }
.ui-icon-alert { background-position: 0 -144px; }
.ui-icon-info { background-position: -16px -144px; }
.ui-icon-notice { background-position: -32px -144px; }
.ui-icon-help { background-position: -48px -144px; }
.ui-icon-check { background-position: -64px -144px; }
.ui-icon-bullet { background-position: -80px -144px; }
.ui-icon-radio-on { background-position: -96px -144px; }
.ui-icon-radio-off { background-position: -112px -144px; }
.ui-icon-pin-w { background-position: -128px -144px; }
.ui-icon-pin-s { background-position: -144px -144px; }
.ui-icon-play { background-position: 0 -160px; }
.ui-icon-pause { background-position: -16px -160px; }
.ui-icon-seek-next { background-position: -32px -160px; }
.ui-icon-seek-prev { background-position: -48px -160px; }
.ui-icon-seek-end { background-position: -64px -160px; }
.ui-icon-seek-start { background-position: -80px -160px; }

.ui-icon-seek-first { background-position: -80px -160px; }
.ui-icon-stop { background-position: -96px -160px; }
.ui-icon-eject { background-position: -112px -160px; }
.ui-icon-volume-off { background-position: -128px -160px; }
.ui-icon-volume-on { background-position: -144px -160px; }
.ui-icon-power { background-position: 0 -176px; }
.ui-icon-signal-diag { background-position: -16px -176px; }
.ui-icon-signal { background-position: -32px -176px; }
.ui-icon-battery-0 { background-position: -48px -176px; }
.ui-icon-battery-1 { background-position: -64px -176px; }
.ui-icon-battery-2 { background-position: -80px -176px; }
.ui-icon-battery-3 { background-position: -96px -176px; }
.ui-icon-circle-plus { background-position: 0 -192px; }
.ui-icon-circle-minus { background-position: -16px -192px; }
.ui-icon-circle-close { background-position: -32px -192px; }
.ui-icon-circle-triangle-e { background-position: -48px -192px; }
.ui-icon-circle-triangle-s { background-position: -64px -192px; }
.ui-icon-circle-triangle-w { background-position: -80px -192px; }
.ui-icon-circle-triangle-n { background-position: -96px -192px; }
.ui-icon-circle-arrow-e { background-position: -112px -192px; }
.ui-icon-circle-arrow-s { background-position: -128px -192px; }
.ui-icon-circle-arrow-w { background-position: -144px -192px; }
.ui-icon-circle-arrow-n { background-position: -160px -192px; }
.ui-icon-circle-zoomin { background-position: -176px -192px; }
.ui-icon-circle-zoomout { background-position: -192px -192px; }
.ui-icon-circle-check { background-position: -208px -192px; }
.ui-icon-circlesmall-plus { background-position: 0 -208px; }
.ui-icon-circlesmall-minus { background-position: -16px -208px; }
.ui-icon-circlesmall-close { background-position: -32px -208px; }
.ui-icon-squaresmall-plus { background-position: -48px -208px; }
.ui-icon-squaresmall-minus { background-position: -64px -208px; }
.ui-icon-squaresmall-close { background-position: -80px -208px; }
.ui-icon-grip-dotted-vertical { background-position: 0 -224px; }
.ui-icon-grip-dotted-horizontal { background-position: -16px -224px; }
.ui-icon-grip-solid-vertical { background-position: -32px -224px; }
.ui-icon-grip-solid-horizontal { background-position: -48px -224px; }
.ui-icon-gripsmall-diagonal-se { background-position: -64px -224px; }
.ui-icon-grip-diagonal-se { background-position: -80px -224px; }





.ui-corner-all,
.ui-corner-top,
.ui-corner-left,
.ui-corner-tl {
	border-top-left-radius: 3px;
}
.ui-corner-all,
.ui-corner-top,
.ui-corner-right,
.ui-corner-tr {
	border-top-right-radius: 3px;
}
.ui-corner-all,
.ui-corner-bottom,
.ui-corner-left,
.ui-corner-bl {
	border-bottom-left-radius: 3px;
}
.ui-corner-all,
.ui-corner-bottom,
.ui-corner-right,
.ui-corner-br {
	border-bottom-right-radius: 3px;
}


.ui-widget-overlay {
	background: #aaaaaa;
	opacity: .3;
	filter: Alpha(Opacity=30); 
}
.ui-widget-shadow {
	-webkit-box-shadow: 0px 0px 5px #666666;
	box-shadow: 0px 0px 5px #666666;
} 
</style>
<script src='js/jquery-1.12.4.js'></script>
<script src='js/jquery-ui.js'></script>

<script>
$( function() {
	$( '#tabs-collect-classes-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-collect-classes-from-hierarchical-partition'>
<ul>
<li><a href='#tab-collect-classes-from-hierarchical-partition-1'>n_signatures ??? 1493</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-2'>n_signatures ??? 2176</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-3'>n_signatures ??? 2235</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-4'>n_signatures ??? 2904</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-5'>n_signatures ??? 3323</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-6'>n_signatures ??? 6134</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-7'>n_signatures ??? 6830</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-8'>n_signatures ??? 8655</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-9'>n_signatures ??? 14245</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-10'>n_signatures ??? 39337</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-11'>n_signatures ??? 39918</a></li>
</ul>
<div id='tab-collect-classes-from-hierarchical-partition-1'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 1493))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-1-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-1"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-2'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2176))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-2-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-2"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-3'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2235))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-3-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-3"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-4'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2904))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-4-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-4"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-5'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3323))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-5-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-5"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-6'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 6134))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-6-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-6"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-7'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 6830))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-7-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-7"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-8'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 8655))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-8-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-8"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-9'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 14245))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-9-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-9"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-10'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 39337))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-10-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-10"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-11'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 39918))
</code></pre>

<pre><code>#&gt; Error in max(children_height): invalid &#39;type&#39; (list) of argument
</code></pre>

</div>
</div>

Following shows the table of the partitions (You need to click the **show/hide
code output** link to see it).


<script>
$( function() {
	$( '#tabs-get-classes-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-get-classes-from-hierarchical-partition'>
<ul>
<li><a href='#tab-get-classes-from-hierarchical-partition-1'>n_signatures ??? 1493</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-2'>n_signatures ??? 2176</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-3'>n_signatures ??? 2235</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-4'>n_signatures ??? 2904</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-5'>n_signatures ??? 3323</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-6'>n_signatures ??? 6134</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-7'>n_signatures ??? 6830</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-8'>n_signatures ??? 8655</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-9'>n_signatures ??? 14245</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-10'>n_signatures ??? 39337</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-11'>n_signatures ??? 39918</a></li>
</ul>

<div id='tab-get-classes-from-hierarchical-partition-1'>
<p><a id='tab-get-classes-from-hierarchical-partition-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 1493))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;          &quot;0321&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;          &quot;0121&quot;           &quot;024&quot;          &quot;0121&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;          &quot;0322&quot;          &quot;0311&quot;           &quot;023&quot;          &quot;0322&quot;          &quot;0321&quot;          &quot;0313&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;          &quot;0412&quot;           &quot;042&quot;          &quot;0122&quot;          &quot;0321&quot;          &quot;0412&quot;          &quot;0411&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;          &quot;0412&quot;           &quot;011&quot;          &quot;0132&quot;          &quot;0323&quot;          &quot;0321&quot;          &quot;0121&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;          &quot;0411&quot;          &quot;0411&quot;           &quot;024&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0322&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;          &quot;0122&quot;          &quot;0123&quot;          &quot;0322&quot;          &quot;0221&quot;           &quot;023&quot;          &quot;0322&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;          &quot;0312&quot;          &quot;0223&quot;          &quot;0412&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;          &quot;0132&quot;          &quot;0122&quot;          &quot;0223&quot;          &quot;0132&quot;           &quot;011&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;          &quot;0312&quot;          &quot;0323&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;           &quot;033&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;          &quot;0321&quot;          &quot;0411&quot;          &quot;0222&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0123&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;          &quot;0322&quot;           &quot;011&quot;           &quot;033&quot;          &quot;0122&quot;          &quot;0123&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;          &quot;0322&quot;          &quot;0121&quot;           &quot;011&quot;          &quot;0313&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;           &quot;011&quot;          &quot;0222&quot;           &quot;021&quot;          &quot;0132&quot;          &quot;0132&quot;           &quot;011&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;          &quot;0311&quot;           &quot;011&quot;           &quot;042&quot;          &quot;0221&quot;          &quot;0311&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;          &quot;0311&quot;          &quot;0223&quot;           &quot;021&quot;          &quot;0312&quot;          &quot;0311&quot;          &quot;0121&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;           &quot;011&quot;          &quot;0412&quot;           &quot;042&quot;           &quot;024&quot;           &quot;011&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;          &quot;0311&quot;          &quot;0121&quot;          &quot;0122&quot;          &quot;0411&quot;           &quot;021&quot;          &quot;0121&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;          &quot;0321&quot;          &quot;0322&quot;          &quot;0412&quot;          &quot;0221&quot;          &quot;0313&quot;           &quot;033&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;          &quot;0412&quot;          &quot;0222&quot;          &quot;0221&quot;          &quot;0312&quot;           &quot;021&quot;           &quot;011&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;          &quot;0321&quot;           &quot;021&quot;          &quot;0131&quot;          &quot;0411&quot;          &quot;0132&quot;          &quot;0121&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;          &quot;0411&quot;          &quot;0311&quot;          &quot;0411&quot;          &quot;0321&quot;          &quot;0131&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;          &quot;0121&quot;           &quot;042&quot;          &quot;0132&quot;          &quot;0121&quot;           &quot;023&quot;          &quot;0131&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;          &quot;0132&quot;           &quot;011&quot;           &quot;024&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;          &quot;0123&quot;          &quot;0322&quot;          &quot;0312&quot;          &quot;0312&quot;          &quot;0131&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;           &quot;033&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;           &quot;033&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;          &quot;0123&quot;           &quot;023&quot;           &quot;033&quot;          &quot;0122&quot;           &quot;011&quot;          &quot;0122&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;          &quot;0311&quot;          &quot;0121&quot;          &quot;0131&quot;           &quot;024&quot;          &quot;0121&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;          &quot;0323&quot;          &quot;0313&quot;           &quot;011&quot;           &quot;011&quot;           &quot;033&quot;          &quot;0412&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;          &quot;0412&quot;           &quot;042&quot;           &quot;042&quot;          &quot;0313&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;          &quot;0311&quot;          &quot;0131&quot;          &quot;0132&quot;           &quot;033&quot;          &quot;0121&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;           &quot;011&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-1-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-1-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-2'>
<p><a id='tab-get-classes-from-hierarchical-partition-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2176))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;          &quot;0321&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;          &quot;0121&quot;           &quot;024&quot;          &quot;0121&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;          &quot;0322&quot;          &quot;0311&quot;           &quot;023&quot;          &quot;0322&quot;          &quot;0321&quot;          &quot;0313&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;          &quot;0412&quot;           &quot;042&quot;          &quot;0122&quot;          &quot;0321&quot;          &quot;0412&quot;          &quot;0411&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;          &quot;0412&quot;           &quot;011&quot;           &quot;013&quot;          &quot;0323&quot;          &quot;0321&quot;          &quot;0121&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;          &quot;0411&quot;          &quot;0411&quot;           &quot;024&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0322&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;          &quot;0122&quot;          &quot;0123&quot;          &quot;0322&quot;          &quot;0221&quot;           &quot;023&quot;          &quot;0322&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;          &quot;0312&quot;          &quot;0223&quot;          &quot;0412&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;           &quot;013&quot;          &quot;0122&quot;          &quot;0223&quot;           &quot;013&quot;           &quot;011&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;          &quot;0312&quot;          &quot;0323&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;           &quot;033&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;          &quot;0321&quot;          &quot;0411&quot;          &quot;0222&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0123&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;          &quot;0322&quot;           &quot;011&quot;           &quot;033&quot;          &quot;0122&quot;          &quot;0123&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;          &quot;0322&quot;          &quot;0121&quot;           &quot;011&quot;          &quot;0313&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;           &quot;011&quot;          &quot;0222&quot;           &quot;021&quot;           &quot;013&quot;           &quot;013&quot;           &quot;011&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;          &quot;0311&quot;           &quot;011&quot;           &quot;042&quot;          &quot;0221&quot;          &quot;0311&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;          &quot;0311&quot;          &quot;0223&quot;           &quot;021&quot;          &quot;0312&quot;          &quot;0311&quot;          &quot;0121&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;           &quot;011&quot;          &quot;0412&quot;           &quot;042&quot;           &quot;024&quot;           &quot;011&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;          &quot;0311&quot;          &quot;0121&quot;          &quot;0122&quot;          &quot;0411&quot;           &quot;021&quot;          &quot;0121&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;          &quot;0321&quot;          &quot;0322&quot;          &quot;0412&quot;          &quot;0221&quot;          &quot;0313&quot;           &quot;033&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;          &quot;0412&quot;          &quot;0222&quot;          &quot;0221&quot;          &quot;0312&quot;           &quot;021&quot;           &quot;011&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;          &quot;0321&quot;           &quot;021&quot;           &quot;013&quot;          &quot;0411&quot;           &quot;013&quot;          &quot;0121&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;          &quot;0411&quot;          &quot;0311&quot;          &quot;0411&quot;          &quot;0321&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;          &quot;0121&quot;           &quot;042&quot;           &quot;013&quot;          &quot;0121&quot;           &quot;023&quot;           &quot;013&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;           &quot;013&quot;           &quot;011&quot;           &quot;024&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;          &quot;0123&quot;          &quot;0322&quot;          &quot;0312&quot;          &quot;0312&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;           &quot;033&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;           &quot;033&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;          &quot;0123&quot;           &quot;023&quot;           &quot;033&quot;          &quot;0122&quot;           &quot;011&quot;          &quot;0122&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;          &quot;0311&quot;          &quot;0121&quot;           &quot;013&quot;           &quot;024&quot;          &quot;0121&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;          &quot;0323&quot;          &quot;0313&quot;           &quot;011&quot;           &quot;011&quot;           &quot;033&quot;          &quot;0412&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;          &quot;0412&quot;           &quot;042&quot;           &quot;042&quot;          &quot;0313&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;          &quot;0311&quot;           &quot;013&quot;           &quot;013&quot;           &quot;033&quot;          &quot;0121&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;           &quot;011&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-2-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-2-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-3'>
<p><a id='tab-get-classes-from-hierarchical-partition-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2235))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;          &quot;0321&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;          &quot;0121&quot;           &quot;024&quot;          &quot;0121&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;          &quot;0322&quot;           &quot;031&quot;           &quot;023&quot;          &quot;0322&quot;          &quot;0321&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;          &quot;0412&quot;           &quot;042&quot;          &quot;0122&quot;          &quot;0321&quot;          &quot;0412&quot;          &quot;0411&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;          &quot;0412&quot;           &quot;011&quot;           &quot;013&quot;          &quot;0323&quot;          &quot;0321&quot;          &quot;0121&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;          &quot;0411&quot;          &quot;0411&quot;           &quot;024&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0322&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;          &quot;0122&quot;          &quot;0123&quot;          &quot;0322&quot;          &quot;0221&quot;           &quot;023&quot;          &quot;0322&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;          &quot;0412&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;           &quot;013&quot;          &quot;0122&quot;          &quot;0223&quot;           &quot;013&quot;           &quot;011&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;           &quot;031&quot;          &quot;0323&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;           &quot;033&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;          &quot;0321&quot;          &quot;0411&quot;          &quot;0222&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0123&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;          &quot;0322&quot;           &quot;011&quot;           &quot;033&quot;          &quot;0122&quot;          &quot;0123&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;          &quot;0322&quot;          &quot;0121&quot;           &quot;011&quot;           &quot;031&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;           &quot;011&quot;          &quot;0222&quot;           &quot;021&quot;           &quot;013&quot;           &quot;013&quot;           &quot;011&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;           &quot;031&quot;           &quot;011&quot;           &quot;042&quot;          &quot;0221&quot;           &quot;031&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;021&quot;           &quot;031&quot;           &quot;031&quot;          &quot;0121&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;           &quot;011&quot;          &quot;0412&quot;           &quot;042&quot;           &quot;024&quot;           &quot;011&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;           &quot;031&quot;          &quot;0121&quot;          &quot;0122&quot;          &quot;0411&quot;           &quot;021&quot;          &quot;0121&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;          &quot;0321&quot;          &quot;0322&quot;          &quot;0412&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;033&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;          &quot;0412&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;021&quot;           &quot;011&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;          &quot;0321&quot;           &quot;021&quot;           &quot;013&quot;          &quot;0411&quot;           &quot;013&quot;          &quot;0121&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;          &quot;0411&quot;           &quot;031&quot;          &quot;0411&quot;          &quot;0321&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;          &quot;0121&quot;           &quot;042&quot;           &quot;013&quot;          &quot;0121&quot;           &quot;023&quot;           &quot;013&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;           &quot;013&quot;           &quot;011&quot;           &quot;024&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;          &quot;0123&quot;          &quot;0322&quot;           &quot;031&quot;           &quot;031&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;           &quot;033&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;           &quot;033&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;          &quot;0123&quot;           &quot;023&quot;           &quot;033&quot;          &quot;0122&quot;           &quot;011&quot;          &quot;0122&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;           &quot;031&quot;          &quot;0121&quot;           &quot;013&quot;           &quot;024&quot;          &quot;0121&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;          &quot;0323&quot;           &quot;031&quot;           &quot;011&quot;           &quot;011&quot;           &quot;033&quot;          &quot;0412&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;          &quot;0412&quot;           &quot;042&quot;           &quot;042&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;           &quot;031&quot;           &quot;013&quot;           &quot;013&quot;           &quot;033&quot;          &quot;0121&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;           &quot;011&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-3-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-3-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-4'>
<p><a id='tab-get-classes-from-hierarchical-partition-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2904))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;          &quot;0321&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;          &quot;0121&quot;           &quot;024&quot;          &quot;0121&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;          &quot;0322&quot;           &quot;031&quot;           &quot;023&quot;          &quot;0322&quot;          &quot;0321&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;           &quot;041&quot;           &quot;042&quot;          &quot;0122&quot;          &quot;0321&quot;           &quot;041&quot;           &quot;041&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;           &quot;041&quot;           &quot;011&quot;           &quot;013&quot;          &quot;0323&quot;          &quot;0321&quot;          &quot;0121&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;           &quot;041&quot;           &quot;041&quot;           &quot;024&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0322&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;          &quot;0122&quot;          &quot;0123&quot;          &quot;0322&quot;          &quot;0221&quot;           &quot;023&quot;          &quot;0322&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;041&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;           &quot;013&quot;          &quot;0122&quot;          &quot;0223&quot;           &quot;013&quot;           &quot;011&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;           &quot;031&quot;          &quot;0323&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;           &quot;033&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;          &quot;0321&quot;           &quot;041&quot;          &quot;0222&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0123&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;          &quot;0322&quot;           &quot;011&quot;           &quot;033&quot;          &quot;0122&quot;          &quot;0123&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;          &quot;0322&quot;          &quot;0121&quot;           &quot;011&quot;           &quot;031&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;           &quot;011&quot;          &quot;0222&quot;           &quot;021&quot;           &quot;013&quot;           &quot;013&quot;           &quot;011&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;           &quot;031&quot;           &quot;011&quot;           &quot;042&quot;          &quot;0221&quot;           &quot;031&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;021&quot;           &quot;031&quot;           &quot;031&quot;          &quot;0121&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;           &quot;011&quot;           &quot;041&quot;           &quot;042&quot;           &quot;024&quot;           &quot;011&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;           &quot;031&quot;          &quot;0121&quot;          &quot;0122&quot;           &quot;041&quot;           &quot;021&quot;          &quot;0121&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;          &quot;0321&quot;          &quot;0322&quot;           &quot;041&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;033&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;           &quot;041&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;021&quot;           &quot;011&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;          &quot;0321&quot;           &quot;021&quot;           &quot;013&quot;           &quot;041&quot;           &quot;013&quot;          &quot;0121&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;           &quot;041&quot;           &quot;031&quot;           &quot;041&quot;          &quot;0321&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;          &quot;0121&quot;           &quot;042&quot;           &quot;013&quot;          &quot;0121&quot;           &quot;023&quot;           &quot;013&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;           &quot;013&quot;           &quot;011&quot;           &quot;024&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;          &quot;0123&quot;          &quot;0322&quot;           &quot;031&quot;           &quot;031&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;           &quot;033&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;           &quot;033&quot;          &quot;0121&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;          &quot;0123&quot;           &quot;023&quot;           &quot;033&quot;          &quot;0122&quot;           &quot;011&quot;          &quot;0122&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;           &quot;031&quot;          &quot;0121&quot;           &quot;013&quot;           &quot;024&quot;          &quot;0121&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;          &quot;0323&quot;           &quot;031&quot;           &quot;011&quot;           &quot;011&quot;           &quot;033&quot;           &quot;041&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;           &quot;041&quot;           &quot;042&quot;           &quot;042&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;           &quot;031&quot;           &quot;013&quot;           &quot;013&quot;           &quot;033&quot;          &quot;0121&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;           &quot;011&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-4-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-4-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-5'>
<p><a id='tab-get-classes-from-hierarchical-partition-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3323))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;          &quot;0321&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;           &quot;012&quot;           &quot;024&quot;           &quot;012&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;          &quot;0322&quot;           &quot;031&quot;           &quot;023&quot;          &quot;0322&quot;          &quot;0321&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;           &quot;041&quot;           &quot;042&quot;           &quot;012&quot;          &quot;0321&quot;           &quot;041&quot;           &quot;041&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;           &quot;041&quot;           &quot;011&quot;           &quot;013&quot;          &quot;0323&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;           &quot;041&quot;           &quot;041&quot;           &quot;024&quot;           &quot;011&quot;           &quot;011&quot;          &quot;0322&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;           &quot;012&quot;           &quot;012&quot;          &quot;0322&quot;          &quot;0221&quot;           &quot;023&quot;          &quot;0322&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;041&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;           &quot;013&quot;           &quot;012&quot;          &quot;0223&quot;           &quot;013&quot;           &quot;011&quot;           &quot;012&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;           &quot;031&quot;          &quot;0323&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;           &quot;033&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;          &quot;0321&quot;           &quot;041&quot;          &quot;0222&quot;           &quot;011&quot;           &quot;011&quot;           &quot;012&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;          &quot;0322&quot;           &quot;011&quot;           &quot;033&quot;           &quot;012&quot;           &quot;012&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;          &quot;0322&quot;           &quot;012&quot;           &quot;011&quot;           &quot;031&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;           &quot;011&quot;          &quot;0222&quot;           &quot;021&quot;           &quot;013&quot;           &quot;013&quot;           &quot;011&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;           &quot;031&quot;           &quot;011&quot;           &quot;042&quot;          &quot;0221&quot;           &quot;031&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;021&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;           &quot;011&quot;           &quot;041&quot;           &quot;042&quot;           &quot;024&quot;           &quot;011&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;           &quot;031&quot;           &quot;012&quot;           &quot;012&quot;           &quot;041&quot;           &quot;021&quot;           &quot;012&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;          &quot;0321&quot;          &quot;0322&quot;           &quot;041&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;033&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;           &quot;041&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;021&quot;           &quot;011&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;          &quot;0321&quot;           &quot;021&quot;           &quot;013&quot;           &quot;041&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;           &quot;041&quot;           &quot;031&quot;           &quot;041&quot;          &quot;0321&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;           &quot;012&quot;           &quot;042&quot;           &quot;013&quot;           &quot;012&quot;           &quot;023&quot;           &quot;013&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;           &quot;013&quot;           &quot;011&quot;           &quot;024&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;           &quot;012&quot;          &quot;0322&quot;           &quot;031&quot;           &quot;031&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;           &quot;033&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;           &quot;033&quot;           &quot;012&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;           &quot;012&quot;           &quot;023&quot;           &quot;033&quot;           &quot;012&quot;           &quot;011&quot;           &quot;012&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;           &quot;031&quot;           &quot;012&quot;           &quot;013&quot;           &quot;024&quot;           &quot;012&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;          &quot;0323&quot;           &quot;031&quot;           &quot;011&quot;           &quot;011&quot;           &quot;033&quot;           &quot;041&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;           &quot;041&quot;           &quot;042&quot;           &quot;042&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;           &quot;031&quot;           &quot;013&quot;           &quot;013&quot;           &quot;033&quot;           &quot;012&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;           &quot;011&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-5-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-5-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-6'>
<p><a id='tab-get-classes-from-hierarchical-partition-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 6134))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;           &quot;032&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;           &quot;012&quot;           &quot;024&quot;           &quot;012&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;           &quot;032&quot;           &quot;031&quot;           &quot;023&quot;           &quot;032&quot;           &quot;032&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;           &quot;041&quot;           &quot;042&quot;           &quot;012&quot;           &quot;032&quot;           &quot;041&quot;           &quot;041&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;           &quot;041&quot;           &quot;011&quot;           &quot;013&quot;           &quot;032&quot;           &quot;032&quot;           &quot;012&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;           &quot;041&quot;           &quot;041&quot;           &quot;024&quot;           &quot;011&quot;           &quot;011&quot;           &quot;032&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;           &quot;012&quot;           &quot;012&quot;           &quot;032&quot;          &quot;0221&quot;           &quot;023&quot;           &quot;032&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;041&quot;           &quot;011&quot;           &quot;032&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;           &quot;013&quot;           &quot;012&quot;          &quot;0223&quot;           &quot;013&quot;           &quot;011&quot;           &quot;012&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;           &quot;031&quot;           &quot;032&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;           &quot;033&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;           &quot;032&quot;           &quot;041&quot;          &quot;0222&quot;           &quot;011&quot;           &quot;011&quot;           &quot;012&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;           &quot;032&quot;           &quot;011&quot;           &quot;033&quot;           &quot;012&quot;           &quot;012&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;           &quot;032&quot;           &quot;012&quot;           &quot;011&quot;           &quot;031&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;           &quot;011&quot;          &quot;0222&quot;           &quot;021&quot;           &quot;013&quot;           &quot;013&quot;           &quot;011&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;           &quot;031&quot;           &quot;011&quot;           &quot;042&quot;          &quot;0221&quot;           &quot;031&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;021&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;           &quot;011&quot;           &quot;041&quot;           &quot;042&quot;           &quot;024&quot;           &quot;011&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;           &quot;031&quot;           &quot;012&quot;           &quot;012&quot;           &quot;041&quot;           &quot;021&quot;           &quot;012&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;           &quot;032&quot;           &quot;032&quot;           &quot;041&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;033&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;           &quot;041&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;021&quot;           &quot;011&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;           &quot;032&quot;           &quot;021&quot;           &quot;013&quot;           &quot;041&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;           &quot;041&quot;           &quot;031&quot;           &quot;041&quot;           &quot;032&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;           &quot;012&quot;           &quot;042&quot;           &quot;013&quot;           &quot;012&quot;           &quot;023&quot;           &quot;013&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;           &quot;013&quot;           &quot;011&quot;           &quot;024&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;           &quot;012&quot;           &quot;032&quot;           &quot;031&quot;           &quot;031&quot;           &quot;013&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;           &quot;033&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;           &quot;033&quot;           &quot;012&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;           &quot;012&quot;           &quot;023&quot;           &quot;033&quot;           &quot;012&quot;           &quot;011&quot;           &quot;012&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;           &quot;031&quot;           &quot;012&quot;           &quot;013&quot;           &quot;024&quot;           &quot;012&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;           &quot;032&quot;           &quot;031&quot;           &quot;011&quot;           &quot;011&quot;           &quot;033&quot;           &quot;041&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;           &quot;041&quot;           &quot;042&quot;           &quot;042&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;           &quot;031&quot;           &quot;013&quot;           &quot;013&quot;           &quot;033&quot;           &quot;012&quot;           &quot;011&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;           &quot;011&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-6-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-6-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-7'>
<p><a id='tab-get-classes-from-hierarchical-partition-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 6830))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;           &quot;032&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;           &quot;032&quot;           &quot;031&quot;           &quot;023&quot;           &quot;032&quot;           &quot;032&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;           &quot;041&quot;           &quot;042&quot;            &quot;01&quot;           &quot;032&quot;           &quot;041&quot;           &quot;041&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;           &quot;041&quot;            &quot;01&quot;            &quot;01&quot;           &quot;032&quot;           &quot;032&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;           &quot;041&quot;           &quot;041&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;           &quot;032&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;            &quot;01&quot;            &quot;01&quot;           &quot;032&quot;          &quot;0221&quot;           &quot;023&quot;           &quot;032&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;041&quot;            &quot;01&quot;           &quot;032&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;            &quot;01&quot;            &quot;01&quot;          &quot;0223&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;           &quot;031&quot;           &quot;032&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;           &quot;033&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;           &quot;032&quot;           &quot;041&quot;          &quot;0222&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;           &quot;032&quot;            &quot;01&quot;           &quot;033&quot;            &quot;01&quot;            &quot;01&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;           &quot;032&quot;            &quot;01&quot;            &quot;01&quot;           &quot;031&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;            &quot;01&quot;          &quot;0222&quot;           &quot;021&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;           &quot;031&quot;            &quot;01&quot;           &quot;042&quot;          &quot;0221&quot;           &quot;031&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;           &quot;031&quot;          &quot;0223&quot;           &quot;021&quot;           &quot;031&quot;           &quot;031&quot;            &quot;01&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;            &quot;01&quot;           &quot;041&quot;           &quot;042&quot;           &quot;024&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;           &quot;031&quot;            &quot;01&quot;            &quot;01&quot;           &quot;041&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;           &quot;032&quot;           &quot;032&quot;           &quot;041&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;033&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;           &quot;041&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;031&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;           &quot;032&quot;           &quot;021&quot;            &quot;01&quot;           &quot;041&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;           &quot;041&quot;           &quot;031&quot;           &quot;041&quot;           &quot;032&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;            &quot;01&quot;           &quot;042&quot;            &quot;01&quot;            &quot;01&quot;           &quot;023&quot;            &quot;01&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;          &quot;0221&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;            &quot;01&quot;           &quot;032&quot;           &quot;031&quot;           &quot;031&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;           &quot;033&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;           &quot;033&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;            &quot;01&quot;           &quot;023&quot;           &quot;033&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;           &quot;031&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;           &quot;032&quot;           &quot;031&quot;            &quot;01&quot;            &quot;01&quot;           &quot;033&quot;           &quot;041&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;           &quot;041&quot;           &quot;042&quot;           &quot;042&quot;           &quot;031&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;           &quot;031&quot;            &quot;01&quot;            &quot;01&quot;           &quot;033&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;            &quot;01&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-7-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-7-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-8'>
<p><a id='tab-get-classes-from-hierarchical-partition-8-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 8655))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;          &quot;0221&quot;           &quot;021&quot;            &quot;03&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;          &quot;0221&quot;          &quot;0223&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;023&quot;            &quot;03&quot;            &quot;03&quot;            &quot;03&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;           &quot;041&quot;           &quot;042&quot;            &quot;01&quot;            &quot;03&quot;           &quot;041&quot;           &quot;041&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;           &quot;041&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;           &quot;041&quot;           &quot;041&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;          &quot;0221&quot;           &quot;023&quot;            &quot;03&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;            &quot;03&quot;          &quot;0223&quot;           &quot;041&quot;            &quot;01&quot;            &quot;03&quot;          &quot;0222&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;            &quot;01&quot;            &quot;01&quot;          &quot;0223&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;            &quot;03&quot;            &quot;03&quot;          &quot;0222&quot;          &quot;0221&quot;           &quot;043&quot;            &quot;03&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;            &quot;03&quot;           &quot;041&quot;          &quot;0222&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;          &quot;0222&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;            &quot;01&quot;          &quot;0222&quot;           &quot;021&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;            &quot;03&quot;            &quot;01&quot;           &quot;042&quot;          &quot;0221&quot;            &quot;03&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;            &quot;03&quot;          &quot;0223&quot;           &quot;021&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;            &quot;01&quot;           &quot;041&quot;           &quot;042&quot;           &quot;024&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;           &quot;041&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;041&quot;          &quot;0221&quot;            &quot;03&quot;            &quot;03&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;           &quot;041&quot;          &quot;0222&quot;          &quot;0221&quot;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot;           &quot;041&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;           &quot;041&quot;            &quot;03&quot;           &quot;041&quot;            &quot;03&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;            &quot;01&quot;           &quot;042&quot;            &quot;01&quot;            &quot;01&quot;           &quot;023&quot;            &quot;01&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;          &quot;0221&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;            &quot;03&quot;           &quot;043&quot;          &quot;0223&quot;           &quot;024&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;            &quot;01&quot;           &quot;023&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;           &quot;041&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;           &quot;041&quot;           &quot;042&quot;           &quot;042&quot;            &quot;03&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;            &quot;01&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-8-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-8-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-8-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-9'>
<p><a id='tab-get-classes-from-hierarchical-partition-9-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 14245))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;           &quot;022&quot;           &quot;021&quot;            &quot;03&quot;           &quot;043&quot;           &quot;043&quot;           &quot;042&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;           &quot;022&quot;           &quot;022&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;023&quot;            &quot;03&quot;            &quot;03&quot;            &quot;03&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;           &quot;041&quot;           &quot;042&quot;            &quot;01&quot;            &quot;03&quot;           &quot;041&quot;           &quot;041&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;           &quot;041&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;           &quot;041&quot;           &quot;041&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;           &quot;022&quot;           &quot;023&quot;            &quot;03&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;            &quot;03&quot;           &quot;022&quot;           &quot;041&quot;            &quot;01&quot;            &quot;03&quot;           &quot;022&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;            &quot;01&quot;            &quot;01&quot;           &quot;022&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;022&quot;           &quot;022&quot;           &quot;043&quot;            &quot;03&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;            &quot;03&quot;           &quot;041&quot;           &quot;022&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;           &quot;022&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;           &quot;024&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;            &quot;01&quot;           &quot;022&quot;           &quot;021&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;           &quot;042&quot;            &quot;03&quot;            &quot;01&quot;           &quot;042&quot;           &quot;022&quot;            &quot;03&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;            &quot;03&quot;           &quot;022&quot;           &quot;021&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;            &quot;01&quot;           &quot;041&quot;           &quot;042&quot;           &quot;024&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;           &quot;041&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;041&quot;           &quot;022&quot;            &quot;03&quot;            &quot;03&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;           &quot;041&quot;           &quot;022&quot;           &quot;022&quot;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot;           &quot;041&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;           &quot;041&quot;            &quot;03&quot;           &quot;041&quot;            &quot;03&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;            &quot;01&quot;           &quot;042&quot;            &quot;01&quot;            &quot;01&quot;           &quot;023&quot;            &quot;01&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;           &quot;022&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;           &quot;042&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;            &quot;03&quot;           &quot;043&quot;           &quot;022&quot;           &quot;024&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;            &quot;01&quot;           &quot;023&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;           &quot;041&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;           &quot;042&quot;           &quot;021&quot;           &quot;041&quot;           &quot;042&quot;           &quot;042&quot;            &quot;03&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;            &quot;01&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-9-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-9-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-9-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-10'>
<p><a id='tab-get-classes-from-hierarchical-partition-10-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 39337))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;           &quot;022&quot;           &quot;021&quot;            &quot;03&quot;            &quot;04&quot;            &quot;04&quot;            &quot;04&quot; 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;           &quot;022&quot;           &quot;022&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot;           &quot;023&quot; 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;023&quot;            &quot;03&quot;            &quot;03&quot;            &quot;03&quot; 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;            &quot;04&quot;            &quot;04&quot;            &quot;01&quot;            &quot;03&quot;            &quot;04&quot;            &quot;04&quot; 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;            &quot;04&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;            &quot;04&quot;            &quot;04&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;           &quot;022&quot;           &quot;023&quot;            &quot;03&quot; 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;            &quot;03&quot;           &quot;022&quot;            &quot;04&quot;            &quot;01&quot;            &quot;03&quot;           &quot;022&quot; 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;            &quot;01&quot;            &quot;01&quot;           &quot;022&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;022&quot;           &quot;022&quot;            &quot;04&quot;            &quot;03&quot; 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;            &quot;03&quot;            &quot;04&quot;           &quot;022&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;           &quot;022&quot; 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;           &quot;024&quot;            &quot;04&quot; 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;            &quot;01&quot;           &quot;022&quot;           &quot;021&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;            &quot;04&quot;            &quot;03&quot;            &quot;01&quot;            &quot;04&quot;           &quot;022&quot;            &quot;03&quot; 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;            &quot;03&quot;           &quot;022&quot;           &quot;021&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;            &quot;01&quot;            &quot;04&quot;            &quot;04&quot;           &quot;024&quot;            &quot;01&quot;            &quot;04&quot; 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;04&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;04&quot;           &quot;022&quot;            &quot;03&quot;            &quot;03&quot; 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;            &quot;04&quot;           &quot;022&quot;           &quot;022&quot;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot;            &quot;04&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;            &quot;04&quot;            &quot;03&quot;            &quot;04&quot;            &quot;03&quot;            &quot;01&quot;            &quot;04&quot; 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;            &quot;01&quot;            &quot;04&quot;            &quot;01&quot;            &quot;01&quot;           &quot;023&quot;            &quot;01&quot; 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;           &quot;022&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;04&quot; 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;            &quot;03&quot;            &quot;04&quot;           &quot;022&quot;           &quot;024&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;            &quot;01&quot;           &quot;023&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;           &quot;021&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;04&quot; 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;            &quot;04&quot;           &quot;021&quot;            &quot;04&quot;            &quot;04&quot;            &quot;04&quot;            &quot;03&quot; 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.RW.A67Y.01 
#&gt;            &quot;01&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-10-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-10-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-10-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-11'>
<p><a id='tab-get-classes-from-hierarchical-partition-11-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 39918))
</code></pre>

<pre><code>#&gt; TCGA.QR.A6H6.01 TCGA.QR.A6GZ.01 TCGA.WB.A81K.01 TCGA.RW.A68D.01 TCGA.RT.A6Y9.01 TCGA.QR.A7IN.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QR.A7IP.01 TCGA.W2.A7H7.01 TCGA.WB.A80N.01 TCGA.QR.A6H0.01 TCGA.RW.A689.01 TCGA.P8.A5KC.11 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QR.A70O.01 TCGA.QR.A700.01 TCGA.SQ.A6I4.11 TCGA.QR.A70C.01 TCGA.WB.A80L.01 TCGA.WB.A81P.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.S7.A7X1.01 TCGA.QT.A7U0.01 TCGA.WB.A81M.01 TCGA.RW.A68A.01 TCGA.RW.A68C.01 TCGA.TT.A6YP.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.RW.A67X.01 TCGA.RW.A688.01 TCGA.W2.A7HF.01 TCGA.WB.A80K.01 TCGA.QT.A5XM.01 TCGA.S7.A7WT.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.SP.A6QH.01 TCGA.QR.A706.01 TCGA.RM.A68W.01 TCGA.S7.A7WX.01 TCGA.WB.A80V.01 TCGA.QR.A70X.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.W2.A7HD.01 TCGA.QR.A70V.01 TCGA.WB.A81H.01 TCGA.QT.A5XJ.01 TCGA.P8.A5KD.11 TCGA.SR.A6MV.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.SR.A6MP.01 TCGA.QR.A70D.01 TCGA.QR.A6GZ.05 TCGA.WB.A81W.01 TCGA.PR.A5PH.01 TCGA.WB.A80P.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QT.A5XK.01 TCGA.SR.A6MY.01 TCGA.RW.A7CZ.01 TCGA.P7.A5NY.01 TCGA.WB.A80Y.01 TCGA.S7.A7WM.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QR.A6GR.01 TCGA.RW.A686.06 TCGA.SR.A6MX.01 TCGA.WB.A822.01 TCGA.QR.A70A.01 TCGA.RW.A684.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.SQ.A6I4.01 TCGA.S7.A7WV.01 TCGA.SR.A6MX.05 TCGA.PR.A5PF.01 TCGA.W2.A7HC.01 TCGA.WB.A81D.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.WB.A821.01 TCGA.RW.A681.01 TCGA.SR.A6MZ.01 TCGA.RT.A6YA.01 TCGA.S7.A7WR.01 TCGA.RW.A680.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.SP.A6QK.01 TCGA.SQ.A6I6.01 TCGA.WB.A81R.01 TCGA.S7.A7WU.01 TCGA.QR.A6H3.01 TCGA.QR.A708.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.WB.A818.01 TCGA.SR.A6MX.06 TCGA.QR.A703.01 TCGA.SP.A6QJ.01 TCGA.P8.A5KD.01 TCGA.QR.A6H2.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.SR.A6N0.01 TCGA.WB.A820.01 TCGA.QR.A6H4.01 TCGA.W2.A7HH.01 TCGA.XG.A823.01 TCGA.WB.A81F.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.WB.A81Q.01 TCGA.WB.A81G.01 TCGA.WB.A814.01 TCGA.TT.A6YJ.01 TCGA.WB.A819.01 TCGA.QR.A70H.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.PR.A5PG.01 TCGA.S7.A7WQ.01 TCGA.P8.A6RY.01 TCGA.QR.A70Q.01 TCGA.RT.A6YC.01 TCGA.SR.A6MR.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.S7.A7WL.01 TCGA.WB.A80M.01 TCGA.WB.A81S.01 TCGA.S7.A7X0.01 TCGA.SP.A6QG.01 TCGA.QR.A70W.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.WB.A817.01 TCGA.RW.A7D0.01 TCGA.TT.A6YK.01 TCGA.SP.A6QD.01 TCGA.WB.A80Q.01 TCGA.SR.A6MQ.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QR.A70N.01 TCGA.QR.A6GT.01 TCGA.QR.A70P.01 TCGA.RW.A685.01 TCGA.QR.A70I.01 TCGA.QR.A70K.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.SP.A6QC.01 TCGA.S7.A7WP.01 TCGA.WB.A81T.01 TCGA.QR.A70J.01 TCGA.S7.A7X2.01 TCGA.W2.A7HB.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.W2.A7UY.01 TCGA.QR.A70G.01 TCGA.QR.A6H5.01 TCGA.WB.A81V.01 TCGA.SP.A6QI.01 TCGA.SA.A6C2.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.RW.A68B.01 TCGA.SR.A6MT.01 TCGA.RW.A67W.01 TCGA.RW.A68G.01 TCGA.TT.A6YO.01 TCGA.QT.A69Q.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.RM.A68T.01 TCGA.QR.A70U.01 TCGA.QR.A6GS.01 TCGA.WB.A81E.01 TCGA.QR.A6GU.01 TCGA.W2.A7HA.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.RW.A67V.01 TCGA.WB.A81N.01 TCGA.WB.A80O.01 TCGA.QT.A5XN.01 TCGA.QR.A70M.01 TCGA.S7.A7WW.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.WB.A816.01 TCGA.QR.A70T.01 TCGA.RW.A68F.01 TCGA.QR.A705.01 TCGA.P7.A5NY.05 TCGA.SP.A6QF.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QR.A707.01 TCGA.S7.A7WO.01 TCGA.W2.A7H5.01 TCGA.QT.A5XO.01 TCGA.QR.A6GW.01 TCGA.WB.A815.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QR.A6ZZ.01 TCGA.RX.A8JQ.01 TCGA.QR.A6H1.01 TCGA.TT.A6YN.01 TCGA.P7.A5NX.01 TCGA.WB.A81J.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.RW.A686.01 TCGA.WB.A81I.01 TCGA.QT.A5XP.01 TCGA.RW.A8AZ.01 TCGA.W2.A7HE.01 TCGA.P8.A5KC.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.QR.A6GX.01 TCGA.P8.A6RX.01 TCGA.QT.A5XL.01 TCGA.WB.A81A.01 TCGA.QR.A70E.01 TCGA.QR.A702.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.S7.A7WN.01 TCGA.QR.A6GO.01 TCGA.SR.A6MS.01 TCGA.SR.A6MU.01 TCGA.QR.A70R.01 TCGA.QR.A6GY.01 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.RW.A67Y.01 
#&gt;              NA
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-11-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-11-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-11-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>



### Top rows heatmap

Heatmaps of the top rows:





```r
top_rows_heatmap(res_rh)
```

![plot of chunk top-rows-heatmap](figure_cola/top-rows-heatmap-1.png)

```
#> Error in h(simpleError(msg, call)) : 
#>   error in evaluating the argument 'object' in selecting a method for function 'draw': no applicable method for 'height' applied to an object of class "list"
```

Top rows on each node:


```r
top_rows_overlap(res_rh, method = "upset")
```

![plot of chunk top-rows-overlap](figure_cola/top-rows-overlap-1.png)


### UMAP plot

UMAP plot which shows how samples are separated.




<script>
$( function() {
	$( '#tabs-dimension-reduction-by-depth' ).tabs();
} );
</script>
<div id='tabs-dimension-reduction-by-depth'>
<ul>
<li><a href='#tab-dimension-reduction-by-depth-1'>n_signatures ??? 1493</a></li>
<li><a href='#tab-dimension-reduction-by-depth-2'>n_signatures ??? 2176</a></li>
<li><a href='#tab-dimension-reduction-by-depth-3'>n_signatures ??? 2235</a></li>
<li><a href='#tab-dimension-reduction-by-depth-4'>n_signatures ??? 2904</a></li>
<li><a href='#tab-dimension-reduction-by-depth-5'>n_signatures ??? 3323</a></li>
<li><a href='#tab-dimension-reduction-by-depth-6'>n_signatures ??? 6134</a></li>
<li><a href='#tab-dimension-reduction-by-depth-7'>n_signatures ??? 6830</a></li>
<li><a href='#tab-dimension-reduction-by-depth-8'>n_signatures ??? 8655</a></li>
<li><a href='#tab-dimension-reduction-by-depth-9'>n_signatures ??? 14245</a></li>
<li><a href='#tab-dimension-reduction-by-depth-10'>n_signatures ??? 39337</a></li>
<li><a href='#tab-dimension-reduction-by-depth-11'>n_signatures ??? 39918</a></li>
</ul>
<div id='tab-dimension-reduction-by-depth-1'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 1493),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 1493),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-1-1.png" title="plot of chunk tab-dimension-reduction-by-depth-1" alt="plot of chunk tab-dimension-reduction-by-depth-1" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-2'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2176),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2176),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-2-1.png" title="plot of chunk tab-dimension-reduction-by-depth-2" alt="plot of chunk tab-dimension-reduction-by-depth-2" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-3'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2235),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2235),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-3-1.png" title="plot of chunk tab-dimension-reduction-by-depth-3" alt="plot of chunk tab-dimension-reduction-by-depth-3" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-4'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2904),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2904),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-4-1.png" title="plot of chunk tab-dimension-reduction-by-depth-4" alt="plot of chunk tab-dimension-reduction-by-depth-4" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-5'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3323),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3323),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-5-1.png" title="plot of chunk tab-dimension-reduction-by-depth-5" alt="plot of chunk tab-dimension-reduction-by-depth-5" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-6'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 6134),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 6134),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-6-1.png" title="plot of chunk tab-dimension-reduction-by-depth-6" alt="plot of chunk tab-dimension-reduction-by-depth-6" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-7'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 6830),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 6830),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-7-1.png" title="plot of chunk tab-dimension-reduction-by-depth-7" alt="plot of chunk tab-dimension-reduction-by-depth-7" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-8'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 8655),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 8655),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-8-1.png" title="plot of chunk tab-dimension-reduction-by-depth-8" alt="plot of chunk tab-dimension-reduction-by-depth-8" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-9'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 14245),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 14245),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-9-1.png" title="plot of chunk tab-dimension-reduction-by-depth-9" alt="plot of chunk tab-dimension-reduction-by-depth-9" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-10'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 39337),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 39337),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-10-1.png" title="plot of chunk tab-dimension-reduction-by-depth-10" alt="plot of chunk tab-dimension-reduction-by-depth-10" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-11'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 39918),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 39918),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-11-1.png" title="plot of chunk tab-dimension-reduction-by-depth-11" alt="plot of chunk tab-dimension-reduction-by-depth-11" width="100%" /></p>

</div>
</div>




### Signature heatmap

Signatures on the heatmap are the union of all signatures found on every node
on the hierarchy. The number of k-means on rows are automatically selected by the function.




<script>
$( function() {
	$( '#tabs-get-signatures-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-get-signatures-from-hierarchical-partition'>
<ul>
<li><a href='#tab-get-signatures-from-hierarchical-partition-1'>n_signatures ??? 1493</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-2'>n_signatures ??? 2176</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-3'>n_signatures ??? 2235</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-4'>n_signatures ??? 2904</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-5'>n_signatures ??? 3323</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-6'>n_signatures ??? 6134</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-7'>n_signatures ??? 6830</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-8'>n_signatures ??? 8655</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-9'>n_signatures ??? 14245</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-10'>n_signatures ??? 39337</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-11'>n_signatures ??? 39918</a></li>
</ul>
<div id='tab-get-signatures-from-hierarchical-partition-1'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 1493))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-1-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-1"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-2'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 2176))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-2-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-2"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-3'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 2235))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-3-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-3"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-4'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 2904))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-4-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-4"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-5'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 3323))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-5-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-5"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-6'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 6134))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-6-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-6"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-7'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 6830))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-7-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-7"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-8'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 8655))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-8-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-8"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-9'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 14245))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-9-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-9"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-10'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 39337))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-10-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-10"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-11'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 39918))
</code></pre>

<pre><code>#&gt; Error in names(x) &lt;- value: &#39;names&#39; attribute [1] must be the same length as the vector [0]
</code></pre>

</div>
</div>




Compare signatures from different nodes:


```r
compare_signatures(res_rh, verbose = FALSE)
```

![plot of chunk unnamed-chunk-24](figure_cola/unnamed-chunk-24-1.png)

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs. Note it only works on every node and the final signatures
are the union of all signatures of all nodes.


```r
# code only for demonstration
# e.g. to show the top 500 most significant rows on each node.
tb = get_signature(res_rh, top_signatures = 500)
```


## Results for each node


---------------------------------------------------




### Node0


Child nodes: 
                [Node01](#Node01)
        ,
                [Node02](#Node02)
        ,
                [Node03](#Node03)
        ,
                [Node04](#Node04)
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["0"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 187 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 4.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-0-collect-plots](figure_cola/node-0-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-0-select-partition-number](figure_cola/node-0-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           0.996       0.998         0.4742 0.526   0.526
#> 3 3 0.983           0.945       0.976         0.3916 0.719   0.508
#> 4 4 0.991           0.958       0.982         0.1216 0.849   0.596
#> 5 5 0.774           0.558       0.777         0.0669 0.896   0.660
#> 6 6 0.774           0.737       0.845         0.0354 0.866   0.516
#> 7 7 0.806           0.690       0.843         0.0249 0.965   0.809
#> 8 8 0.828           0.637       0.811         0.0195 0.976   0.857
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 4
#> attr(,"optional")
#> [1] 2 3
```

There is also optional best $k$ = 2 3 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-0-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-0-get-classes'>
<ul>
<li><a href='#tab-node-0-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-0-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-0-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-0-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-0-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-0-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-0-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-0-get-classes-1'>
<p><a id='tab-node-0-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.QR.A6H6.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A6GZ.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A81K.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A68D.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RT.A6Y9.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A7IN.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A7IP.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.W2.A7H7.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A80N.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6H0.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RW.A689.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.P8.A5KC.11     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70O.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A700.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SQ.A6I4.11     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70C.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80L.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81P.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7X1.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QT.A7U0.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A81M.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A68A.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A68C.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.TT.A6YP.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RW.A67X.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RW.A688.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7HF.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80K.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QT.A5XM.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WT.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SP.A6QH.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A706.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RM.A68W.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.S7.A7WX.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80V.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70X.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7HD.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70V.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81H.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QT.A5XJ.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.P8.A5KD.11     2   0.000      0.998 0.00 1.00
#&gt; TCGA.SR.A6MV.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MP.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70D.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A6GZ.05     1   0.529      0.864 0.88 0.12
#&gt; TCGA.WB.A81W.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.PR.A5PH.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80P.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QT.A5XK.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MY.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A7CZ.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.P7.A5NY.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80Y.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WM.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6GR.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A686.06     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MX.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A822.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70A.01     1   0.327      0.936 0.94 0.06
#&gt; TCGA.RW.A684.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SQ.A6I4.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WV.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.SR.A6MX.05     2   0.000      0.998 0.00 1.00
#&gt; TCGA.PR.A5PF.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7HC.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81D.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A821.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A681.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MZ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RT.A6YA.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WR.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A680.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.SP.A6QK.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SQ.A6I6.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81R.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WU.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6H3.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A708.01     2   0.584      0.837 0.14 0.86
#&gt; TCGA.WB.A818.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MX.06     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A703.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.SP.A6QJ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.P8.A5KD.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6H2.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6N0.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A820.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6H4.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7HH.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.XG.A823.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A81F.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81Q.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81G.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A814.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.TT.A6YJ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A819.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70H.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.PR.A5PG.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WQ.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.P8.A6RY.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70Q.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RT.A6YC.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MR.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.S7.A7WL.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80M.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81S.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7X0.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.SP.A6QG.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70W.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A817.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A7D0.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.TT.A6YK.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.SP.A6QD.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A80Q.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MQ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70N.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A6GT.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70P.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RW.A685.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70I.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70K.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SP.A6QC.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WP.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A81T.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70J.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.S7.A7X2.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7HB.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7UY.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70G.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6H5.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A81V.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SP.A6QI.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SA.A6C2.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RW.A68B.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MT.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RW.A67W.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A68G.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.TT.A6YO.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QT.A69Q.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RM.A68T.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A70U.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6GS.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81E.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A6GU.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.W2.A7HA.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A67V.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81N.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80O.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QT.A5XN.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70M.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WW.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A816.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70T.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RW.A68F.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A705.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.P7.A5NY.05     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SP.A6QF.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A707.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WO.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.W2.A7H5.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QT.A5XO.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6GW.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A815.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6ZZ.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.RX.A8JQ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6H1.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.TT.A6YN.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.P7.A5NX.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A81J.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A686.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81I.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QT.A5XP.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A8AZ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7HE.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.P8.A5KC.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A6GX.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.P8.A6RX.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QT.A5XL.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.WB.A81A.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70E.01     2   0.000      0.998 0.00 1.00
#&gt; TCGA.QR.A702.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WN.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6GO.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MS.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MU.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70R.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A6GY.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A67Y.01     1   0.000      0.998 1.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-1-a').parent().next().next().hide();
$('#tab-node-0-get-classes-1-a').click(function(){
  $('#tab-node-0-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-2'>
<p><a id='tab-node-0-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.QR.A6H6.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A6GZ.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A81K.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A68D.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.RT.A6Y9.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A7IN.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A7IP.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.W2.A7H7.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A80N.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A6H0.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.RW.A689.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.P8.A5KC.11     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70O.01     3  0.5016     0.7180 0.24 0.00 0.76
#&gt; TCGA.QR.A700.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.SQ.A6I4.11     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70C.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A80L.01     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.WB.A81P.01     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.S7.A7X1.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QT.A7U0.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A81M.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A68A.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RW.A68C.01     2  0.2066     0.9378 0.00 0.94 0.06
#&gt; TCGA.TT.A6YP.01     2  0.2066     0.9378 0.00 0.94 0.06
#&gt; TCGA.RW.A67X.01     2  0.5560     0.5976 0.00 0.70 0.30
#&gt; TCGA.RW.A688.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.W2.A7HF.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A80K.01     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.QT.A5XM.01     3  0.5560     0.6270 0.30 0.00 0.70
#&gt; TCGA.S7.A7WT.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A706.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RM.A68W.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.S7.A7WX.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A80V.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A70X.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.W2.A7HD.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A70V.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A81H.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QT.A5XJ.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.P8.A5KD.11     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.SR.A6MV.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.SR.A6MP.01     3  0.5560     0.6270 0.30 0.00 0.70
#&gt; TCGA.QR.A70D.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A6GZ.05     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A81W.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A80P.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QT.A5XK.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6MY.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.P7.A5NY.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A80Y.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7WM.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A6GR.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RW.A686.06     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.SR.A6MX.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A822.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70A.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RW.A684.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.SQ.A6I4.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.S7.A7WV.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.SR.A6MX.05     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.PR.A5PF.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.W2.A7HC.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A81D.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A821.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RW.A681.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6MZ.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RT.A6YA.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7WR.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A680.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.SP.A6QK.01     3  0.4002     0.8162 0.16 0.00 0.84
#&gt; TCGA.SQ.A6I6.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A81R.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A6H3.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A708.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A818.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6MX.06     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A703.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.SP.A6QJ.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A6H2.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6N0.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A820.01     3  0.5397     0.6594 0.28 0.00 0.72
#&gt; TCGA.QR.A6H4.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.XG.A823.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A81F.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A81Q.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A81G.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A814.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.TT.A6YJ.01     1  0.5216     0.6116 0.74 0.00 0.26
#&gt; TCGA.WB.A819.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A70H.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.PR.A5PG.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     3  0.1529     0.9089 0.00 0.04 0.96
#&gt; TCGA.P8.A6RY.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70Q.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.RT.A6YC.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6MR.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.S7.A7WL.01     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.WB.A80M.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A81S.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7X0.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.SP.A6QG.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70W.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A817.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RW.A7D0.01     1  0.6280     0.0353 0.54 0.00 0.46
#&gt; TCGA.TT.A6YK.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.SP.A6QD.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A80Q.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.SR.A6MQ.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A70N.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A6GT.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70P.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.RW.A685.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A70I.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70K.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SP.A6QC.01     1  0.2537     0.8983 0.92 0.00 0.08
#&gt; TCGA.S7.A7WP.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A81T.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A70J.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.S7.A7X2.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.W2.A7HB.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     3  0.0892     0.9256 0.00 0.02 0.98
#&gt; TCGA.QR.A70G.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A6H5.01     3  0.0892     0.9256 0.00 0.02 0.98
#&gt; TCGA.WB.A81V.01     3  0.5706     0.5908 0.32 0.00 0.68
#&gt; TCGA.SP.A6QI.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.RW.A68B.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6MT.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.RW.A67W.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A68G.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.TT.A6YO.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QT.A69Q.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RM.A68T.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A70U.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A6GS.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A81E.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A6GU.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.W2.A7HA.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A67V.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A81N.01     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.WB.A80O.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QT.A5XN.01     3  0.5560     0.6270 0.30 0.00 0.70
#&gt; TCGA.QR.A70M.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7WW.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.WB.A816.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A70T.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.RW.A68F.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QR.A705.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.P7.A5NY.05     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.SP.A6QF.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A707.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7WO.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.W2.A7H5.01     3  0.6126     0.4139 0.40 0.00 0.60
#&gt; TCGA.QT.A5XO.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A6GW.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.WB.A815.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A6ZZ.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.RX.A8JQ.01     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.QR.A6H1.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.TT.A6YN.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.P7.A5NX.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.WB.A81J.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A686.01     3  0.2066     0.9077 0.06 0.00 0.94
#&gt; TCGA.WB.A81I.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QT.A5XP.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A8AZ.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.W2.A7HE.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.P8.A5KC.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A6GX.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.P8.A6RX.01     2  0.0000     0.9908 0.00 1.00 0.00
#&gt; TCGA.QT.A5XL.01     2  0.2066     0.9378 0.00 0.94 0.06
#&gt; TCGA.WB.A81A.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A70E.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A702.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.S7.A7WN.01     3  0.6045     0.4636 0.38 0.00 0.62
#&gt; TCGA.QR.A6GO.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.SR.A6MU.01     3  0.0000     0.9399 0.00 0.00 1.00
#&gt; TCGA.QR.A70R.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.QR.A6GY.01     1  0.0000     0.9881 1.00 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.0000     0.9881 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-2-a').parent().next().next().hide();
$('#tab-node-0-get-classes-2-a').click(function(){
  $('#tab-node-0-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-3'>
<p><a id='tab-node-0-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.QR.A6H6.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.01     2  0.3801     0.7452 0.00 0.78 0.00 0.22
#&gt; TCGA.WB.A81K.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A68D.01     4  0.1211     0.9336 0.00 0.04 0.00 0.96
#&gt; TCGA.RT.A6Y9.01     4  0.2921     0.8219 0.00 0.14 0.00 0.86
#&gt; TCGA.QR.A7IN.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A7IP.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A80N.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6H0.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.RW.A689.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KC.11     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70O.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A700.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SQ.A6I4.11     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70C.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A80L.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A81P.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7X1.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QT.A7U0.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A81M.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68A.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A68C.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.TT.A6YP.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A67X.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A688.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HF.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80K.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QT.A5XM.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7WT.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A706.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.RM.A68W.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7WX.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80V.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70X.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.W2.A7HD.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70V.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81H.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QT.A5XJ.01     2  0.3801     0.7452 0.00 0.78 0.00 0.22
#&gt; TCGA.P8.A5KD.11     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.SR.A6MV.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SR.A6MP.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70D.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     4  0.0707     0.9520 0.00 0.00 0.02 0.98
#&gt; TCGA.WB.A81W.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A80P.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QT.A5XK.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MY.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.P7.A5NY.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80Y.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WM.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GR.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A686.06     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SR.A6MX.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A822.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70A.01     4  0.3975     0.6793 0.00 0.00 0.24 0.76
#&gt; TCGA.RW.A684.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SQ.A6I4.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7WV.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.SR.A6MX.05     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.PR.A5PF.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HC.01     1  0.1637     0.9320 0.94 0.00 0.06 0.00
#&gt; TCGA.WB.A81D.01     1  0.1637     0.9320 0.94 0.00 0.06 0.00
#&gt; TCGA.WB.A821.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A681.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MZ.01     3  0.4994     0.0569 0.00 0.00 0.52 0.48
#&gt; TCGA.RT.A6YA.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WR.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A680.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SQ.A6I6.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81R.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A6H3.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A708.01     4  0.1637     0.9151 0.00 0.00 0.06 0.94
#&gt; TCGA.WB.A818.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.06     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A703.01     2  0.3610     0.7707 0.00 0.80 0.00 0.20
#&gt; TCGA.SP.A6QJ.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6H2.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6N0.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A820.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A6H4.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.XG.A823.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A81Q.01     3  0.1211     0.9451 0.00 0.00 0.96 0.04
#&gt; TCGA.WB.A81G.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A814.01     2  0.3801     0.7452 0.00 0.78 0.00 0.22
#&gt; TCGA.TT.A6YJ.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A819.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70H.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PG.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.P8.A6RY.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A70Q.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.RT.A6YC.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MR.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.S7.A7WL.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A80M.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81S.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7X0.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.SP.A6QG.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70W.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A817.01     3  0.1211     0.9451 0.00 0.00 0.96 0.04
#&gt; TCGA.RW.A7D0.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.TT.A6YK.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.SP.A6QD.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SR.A6MQ.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70N.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A6GT.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70P.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.RW.A685.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70I.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70K.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QC.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7WP.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A81T.01     1  0.4713     0.4492 0.64 0.00 0.36 0.00
#&gt; TCGA.QR.A70J.01     4  0.3172     0.7936 0.00 0.16 0.00 0.84
#&gt; TCGA.S7.A7X2.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HB.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A70G.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A6H5.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A81V.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SP.A6QI.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A68B.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MT.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A67W.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68G.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YO.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QT.A69Q.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RM.A68T.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GS.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81E.01     2  0.3801     0.7452 0.00 0.78 0.00 0.22
#&gt; TCGA.QR.A6GU.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.W2.A7HA.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67V.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81N.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A80O.01     3  0.0707     0.9613 0.02 0.00 0.98 0.00
#&gt; TCGA.QT.A5XN.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70M.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WW.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A816.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70T.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A68F.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A705.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.P7.A5NY.05     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.SP.A6QF.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A707.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WO.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.W2.A7H5.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QT.A5XO.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GW.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A815.01     1  0.1211     0.9522 0.96 0.00 0.04 0.00
#&gt; TCGA.QR.A6ZZ.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A6H1.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YN.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NX.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A81J.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A686.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A81I.01     3  0.0707     0.9613 0.02 0.00 0.98 0.00
#&gt; TCGA.QT.A5XP.01     1  0.1637     0.9320 0.94 0.00 0.06 0.00
#&gt; TCGA.RW.A8AZ.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HE.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.P8.A5KC.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A6GX.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.P8.A6RX.01     2  0.0000     0.9714 0.00 1.00 0.00 0.00
#&gt; TCGA.QT.A5XL.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A81A.01     4  0.4277     0.6070 0.00 0.00 0.28 0.72
#&gt; TCGA.QR.A70E.01     4  0.0000     0.9683 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A702.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7WN.01     3  0.0000     0.9826 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A6GO.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MU.01     3  0.3610     0.7425 0.00 0.00 0.80 0.20
#&gt; TCGA.QR.A70R.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GY.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.0000     0.9901 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-3-a').parent().next().next().hide();
$('#tab-node-0-get-classes-3-a').click(function(){
  $('#tab-node-0-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-4'>
<p><a id='tab-node-0-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.QR.A6H6.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.01     4  0.3796     0.4879 0.00 0.30 0.00 0.70 0.00
#&gt; TCGA.WB.A81K.01     1  0.6219    -0.7313 0.44 0.00 0.14 0.00 0.42
#&gt; TCGA.RW.A68D.01     4  0.0609     0.8111 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.RT.A6Y9.01     4  0.1648     0.7921 0.00 0.04 0.00 0.94 0.02
#&gt; TCGA.QR.A7IN.01     4  0.3424     0.7557 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.QR.A7IP.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80N.01     1  0.4227     0.6927 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.QR.A6H0.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A689.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.P8.A5KC.11     2  0.1043     0.9507 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.QR.A70O.01     5  0.6265     0.7941 0.24 0.00 0.22 0.00 0.54
#&gt; TCGA.QR.A700.01     3  0.1043     0.5136 0.00 0.00 0.96 0.00 0.04
#&gt; TCGA.SQ.A6I4.11     2  0.1043     0.9507 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.QR.A70C.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.WB.A80L.01     3  0.4227     0.1106 0.00 0.00 0.58 0.00 0.42
#&gt; TCGA.WB.A81P.01     3  0.5131    -0.0982 0.04 0.00 0.54 0.00 0.42
#&gt; TCGA.S7.A7X1.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.QT.A7U0.01     4  0.3424     0.7557 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.WB.A81M.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.RW.A68A.01     3  0.3424     0.5162 0.00 0.00 0.76 0.00 0.24
#&gt; TCGA.RW.A68C.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.TT.A6YP.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.RW.A67X.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.RW.A688.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.W2.A7HF.01     1  0.0609     0.4767 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.WB.A80K.01     3  0.4767     0.0125 0.02 0.00 0.56 0.00 0.42
#&gt; TCGA.QT.A5XM.01     5  0.6671     0.8337 0.24 0.00 0.34 0.00 0.42
#&gt; TCGA.S7.A7WT.01     1  0.3109     0.1762 0.80 0.00 0.00 0.00 0.20
#&gt; TCGA.SP.A6QH.01     4  0.0000     0.8137 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A706.01     4  0.3424     0.7557 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.RM.A68W.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WX.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.WB.A80V.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.QR.A70X.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.W2.A7HD.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.QR.A70V.01     1  0.3684     0.0669 0.72 0.00 0.00 0.00 0.28
#&gt; TCGA.WB.A81H.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.QT.A5XJ.01     4  0.3983     0.4054 0.00 0.34 0.00 0.66 0.00
#&gt; TCGA.P8.A5KD.11     2  0.1043     0.9507 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.SR.A6MV.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.SR.A6MP.01     5  0.6671     0.8337 0.24 0.00 0.34 0.00 0.42
#&gt; TCGA.QR.A70D.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     3  0.3895     0.0876 0.00 0.00 0.68 0.32 0.00
#&gt; TCGA.WB.A81W.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.PR.A5PH.01     3  0.3424     0.5162 0.00 0.00 0.76 0.00 0.24
#&gt; TCGA.WB.A80P.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XK.01     1  0.2516     0.3033 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.SR.A6MY.01     1  0.0000     0.4894 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NY.01     1  0.1410     0.4384 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.WB.A80Y.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.S7.A7WM.01     1  0.3424     0.6425 0.76 0.00 0.00 0.00 0.24
#&gt; TCGA.QR.A6GR.01     3  0.4227     0.1106 0.00 0.00 0.58 0.00 0.42
#&gt; TCGA.RW.A686.06     3  0.5131    -0.0982 0.04 0.00 0.54 0.00 0.42
#&gt; TCGA.SR.A6MX.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A822.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70A.01     3  0.3999     0.2452 0.00 0.00 0.74 0.24 0.02
#&gt; TCGA.RW.A684.01     3  0.4126     0.4265 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.SQ.A6I4.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.S7.A7WV.01     4  0.0000     0.8137 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.SR.A6MX.05     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PF.01     1  0.3424     0.6425 0.76 0.00 0.00 0.00 0.24
#&gt; TCGA.W2.A7HC.01     1  0.3983    -0.2696 0.66 0.00 0.00 0.00 0.34
#&gt; TCGA.WB.A81D.01     1  0.3684    -0.0459 0.72 0.00 0.00 0.00 0.28
#&gt; TCGA.WB.A821.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.RW.A681.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.SR.A6MZ.01     3  0.2280     0.4688 0.00 0.00 0.88 0.12 0.00
#&gt; TCGA.RT.A6YA.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.S7.A7WR.01     1  0.1410     0.5365 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.RW.A680.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     5  0.6671     0.8337 0.24 0.00 0.34 0.00 0.42
#&gt; TCGA.SQ.A6I6.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.WB.A81R.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.S7.A7WU.01     3  0.3424     0.5162 0.00 0.00 0.76 0.00 0.24
#&gt; TCGA.QR.A6H3.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A708.01     3  0.3895     0.0876 0.00 0.00 0.68 0.32 0.00
#&gt; TCGA.WB.A818.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.SR.A6MX.06     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A703.01     4  0.3983     0.4054 0.00 0.34 0.00 0.66 0.00
#&gt; TCGA.SP.A6QJ.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.P8.A5KD.01     1  0.1732     0.3957 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.QR.A6H2.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.SR.A6N0.01     4  0.4798     0.4909 0.00 0.00 0.44 0.54 0.02
#&gt; TCGA.WB.A820.01     5  0.6671     0.8337 0.24 0.00 0.34 0.00 0.42
#&gt; TCGA.QR.A6H4.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.W2.A7HH.01     4  0.3424     0.7557 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.XG.A823.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     1  0.6219    -0.7313 0.44 0.00 0.14 0.00 0.42
#&gt; TCGA.WB.A81Q.01     3  0.0609     0.5013 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.WB.A81G.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A814.01     4  0.3983     0.4054 0.00 0.34 0.00 0.66 0.00
#&gt; TCGA.TT.A6YJ.01     5  0.5927     0.7140 0.34 0.00 0.12 0.00 0.54
#&gt; TCGA.WB.A819.01     1  0.6219    -0.7313 0.44 0.00 0.14 0.00 0.42
#&gt; TCGA.QR.A70H.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.PR.A5PG.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.S7.A7WQ.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.P8.A6RY.01     4  0.0609     0.8111 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.QR.A70Q.01     2  0.1043     0.9507 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.RT.A6YC.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.SR.A6MR.01     3  0.4726    -0.1940 0.00 0.00 0.58 0.40 0.02
#&gt; TCGA.S7.A7WL.01     3  0.4227     0.1106 0.00 0.00 0.58 0.00 0.42
#&gt; TCGA.WB.A80M.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.WB.A81S.01     1  0.0609     0.4693 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.S7.A7X0.01     4  0.3424     0.7557 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.SP.A6QG.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70W.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.WB.A817.01     3  0.0000     0.5055 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.RW.A7D0.01     5  0.6723     0.8182 0.28 0.00 0.30 0.00 0.42
#&gt; TCGA.TT.A6YK.01     4  0.3424     0.7557 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.SP.A6QD.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     3  0.3424     0.5162 0.00 0.00 0.76 0.00 0.24
#&gt; TCGA.SR.A6MQ.01     3  0.4060     0.4541 0.00 0.00 0.64 0.00 0.36
#&gt; TCGA.QR.A70N.01     4  0.3561     0.7405 0.00 0.00 0.26 0.74 0.00
#&gt; TCGA.QR.A6GT.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70P.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A685.01     1  0.6219    -0.7313 0.44 0.00 0.14 0.00 0.42
#&gt; TCGA.QR.A70I.01     2  0.3684     0.6616 0.00 0.72 0.00 0.28 0.00
#&gt; TCGA.QR.A70K.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.SP.A6QC.01     1  0.6219    -0.7313 0.44 0.00 0.14 0.00 0.42
#&gt; TCGA.S7.A7WP.01     2  0.3424     0.7269 0.00 0.76 0.00 0.24 0.00
#&gt; TCGA.WB.A81T.01     1  0.5884    -0.6819 0.48 0.00 0.10 0.00 0.42
#&gt; TCGA.QR.A70J.01     4  0.1410     0.7841 0.00 0.06 0.00 0.94 0.00
#&gt; TCGA.S7.A7X2.01     1  0.2280     0.3365 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.W2.A7HB.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.W2.A7UY.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.QR.A70G.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.QR.A6H5.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.WB.A81V.01     5  0.6671     0.8337 0.24 0.00 0.34 0.00 0.42
#&gt; TCGA.SP.A6QI.01     1  0.3684     0.0669 0.72 0.00 0.00 0.00 0.28
#&gt; TCGA.SA.A6C2.01     4  0.0000     0.8137 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A68B.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.SR.A6MT.01     4  0.0609     0.8111 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.RW.A67W.01     1  0.3424     0.6425 0.76 0.00 0.00 0.00 0.24
#&gt; TCGA.RW.A68G.01     1  0.0000     0.4894 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YO.01     2  0.1043     0.9507 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.QT.A69Q.01     1  0.0000     0.4894 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RM.A68T.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     1  0.3684     0.0669 0.72 0.00 0.00 0.00 0.28
#&gt; TCGA.QR.A6GS.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.WB.A81E.01     4  0.4360     0.4770 0.00 0.30 0.00 0.68 0.02
#&gt; TCGA.QR.A6GU.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HA.01     1  0.2732     0.2672 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.RW.A67V.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.WB.A81N.01     3  0.5178    -0.1626 0.04 0.00 0.48 0.00 0.48
#&gt; TCGA.WB.A80O.01     1  0.6219    -0.7313 0.44 0.00 0.14 0.00 0.42
#&gt; TCGA.QT.A5XN.01     5  0.6265     0.7941 0.24 0.00 0.22 0.00 0.54
#&gt; TCGA.QR.A70M.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.S7.A7WW.01     4  0.3999     0.7520 0.00 0.00 0.24 0.74 0.02
#&gt; TCGA.WB.A816.01     3  0.3561     0.5055 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.QR.A70T.01     3  0.4818    -0.3471 0.00 0.00 0.52 0.46 0.02
#&gt; TCGA.RW.A68F.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A705.01     2  0.0000     0.9688 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NY.05     3  0.1410     0.5171 0.00 0.00 0.94 0.00 0.06
#&gt; TCGA.SP.A6QF.01     1  0.0609     0.4693 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.QR.A707.01     1  0.3424     0.6425 0.76 0.00 0.00 0.00 0.24
#&gt; TCGA.S7.A7WO.01     2  0.1043     0.9507 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.W2.A7H5.01     5  0.6265     0.7941 0.24 0.00 0.22 0.00 0.54
#&gt; TCGA.QT.A5XO.01     1  0.3424     0.6425 0.76 0.00 0.00 0.00 0.24
#&gt; TCGA.QR.A6GW.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.WB.A815.01     1  0.4456    -0.2655 0.66 0.00 0.02 0.00 0.32
#&gt; TCGA.QR.A6ZZ.01     2  0.3424     0.7269 0.00 0.76 0.00 0.24 0.00
#&gt; TCGA.RX.A8JQ.01     3  0.4227     0.1106 0.00 0.00 0.58 0.00 0.42
#&gt; TCGA.QR.A6H1.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.TT.A6YN.01     1  0.3424     0.6425 0.76 0.00 0.00 0.00 0.24
#&gt; TCGA.P7.A5NX.01     2  0.1043     0.9507 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.WB.A81J.01     1  0.3684     0.6554 0.72 0.00 0.00 0.00 0.28
#&gt; TCGA.RW.A686.01     3  0.4767     0.0125 0.02 0.00 0.56 0.00 0.42
#&gt; TCGA.WB.A81I.01     1  0.6219    -0.7313 0.44 0.00 0.14 0.00 0.42
#&gt; TCGA.QT.A5XP.01     1  0.3684    -0.0749 0.72 0.00 0.00 0.00 0.28
#&gt; TCGA.RW.A8AZ.01     1  0.2732     0.2672 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.W2.A7HE.01     3  0.2280     0.5225 0.00 0.00 0.88 0.00 0.12
#&gt; TCGA.P8.A5KC.01     4  0.3424     0.7557 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.QR.A6GX.01     4  0.4182     0.5662 0.00 0.00 0.40 0.60 0.00
#&gt; TCGA.P8.A6RX.01     2  0.0609     0.9603 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.QT.A5XL.01     4  0.1043     0.8206 0.00 0.00 0.04 0.96 0.00
#&gt; TCGA.WB.A81A.01     3  0.2929     0.3983 0.00 0.00 0.82 0.18 0.00
#&gt; TCGA.QR.A70E.01     3  0.4767    -0.2468 0.00 0.00 0.56 0.42 0.02
#&gt; TCGA.QR.A702.01     5  0.4798     0.5963 0.44 0.00 0.02 0.00 0.54
#&gt; TCGA.S7.A7WN.01     5  0.6671     0.8337 0.24 0.00 0.34 0.00 0.42
#&gt; TCGA.QR.A6GO.01     1  0.4227     0.6927 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.SR.A6MS.01     1  0.4227     0.6927 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.SR.A6MU.01     3  0.2020     0.4762 0.00 0.00 0.90 0.10 0.00
#&gt; TCGA.QR.A70R.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.QR.A6GY.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.RW.A67Y.01     1  0.4262     0.6962 0.56 0.00 0.00 0.00 0.44
</code></pre>

<script>
$('#tab-node-0-get-classes-4-a').parent().next().next().hide();
$('#tab-node-0-get-classes-4-a').click(function(){
  $('#tab-node-0-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-5'>
<p><a id='tab-node-0-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.QR.A6H6.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.01     4  0.1267     0.8001 0.00 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.WB.A81K.01     5  0.2631     0.6224 0.00 0.00 0.18 0.00 0.82 0.00
#&gt; TCGA.RW.A68D.01     4  0.0547     0.8210 0.00 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.RT.A6Y9.01     4  0.0547     0.8210 0.00 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.QR.A7IN.01     6  0.3309     0.7092 0.00 0.00 0.00 0.28 0.00 0.72
#&gt; TCGA.QR.A7IP.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80N.01     1  0.2048     0.8042 0.88 0.00 0.00 0.00 0.12 0.00
#&gt; TCGA.QR.A6H0.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A689.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KC.11     2  0.3163     0.8471 0.00 0.82 0.00 0.14 0.04 0.00
#&gt; TCGA.QR.A70O.01     3  0.4845     0.4565 0.00 0.00 0.54 0.00 0.40 0.06
#&gt; TCGA.QR.A700.01     3  0.3797     0.0935 0.00 0.00 0.58 0.00 0.00 0.42
#&gt; TCGA.SQ.A6I4.11     2  0.3163     0.8471 0.00 0.82 0.00 0.14 0.04 0.00
#&gt; TCGA.QR.A70C.01     3  0.1814     0.7092 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.WB.A80L.01     3  0.2941     0.7172 0.00 0.00 0.78 0.00 0.22 0.00
#&gt; TCGA.WB.A81P.01     3  0.2941     0.7140 0.00 0.00 0.78 0.00 0.22 0.00
#&gt; TCGA.S7.A7X1.01     4  0.3756     0.2314 0.00 0.00 0.00 0.60 0.00 0.40
#&gt; TCGA.QT.A7U0.01     6  0.3309     0.7092 0.00 0.00 0.00 0.28 0.00 0.72
#&gt; TCGA.WB.A81M.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68A.01     3  0.2048     0.6961 0.00 0.00 0.88 0.00 0.00 0.12
#&gt; TCGA.RW.A68C.01     4  0.2048     0.7707 0.00 0.00 0.00 0.88 0.00 0.12
#&gt; TCGA.TT.A6YP.01     4  0.2048     0.7707 0.00 0.00 0.00 0.88 0.00 0.12
#&gt; TCGA.RW.A67X.01     4  0.2260     0.7524 0.00 0.00 0.00 0.86 0.00 0.14
#&gt; TCGA.RW.A688.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HF.01     5  0.3578     0.6037 0.34 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.WB.A80K.01     3  0.2941     0.7181 0.00 0.00 0.78 0.00 0.22 0.00
#&gt; TCGA.QT.A5XM.01     3  0.3828     0.4934 0.00 0.00 0.56 0.00 0.44 0.00
#&gt; TCGA.S7.A7WT.01     5  0.2790     0.7743 0.14 0.00 0.02 0.00 0.84 0.00
#&gt; TCGA.SP.A6QH.01     4  0.0000     0.8199 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A706.01     6  0.3309     0.7092 0.00 0.00 0.00 0.28 0.00 0.72
#&gt; TCGA.RM.A68W.01     2  0.0547     0.9510 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.S7.A7WX.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80V.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70X.01     3  0.2094     0.7184 0.00 0.00 0.90 0.00 0.02 0.08
#&gt; TCGA.W2.A7HD.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70V.01     5  0.4519     0.6911 0.10 0.00 0.08 0.00 0.76 0.06
#&gt; TCGA.WB.A81H.01     3  0.1814     0.7092 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.QT.A5XJ.01     4  0.2629     0.7748 0.00 0.08 0.02 0.88 0.02 0.00
#&gt; TCGA.P8.A5KD.11     2  0.3163     0.8471 0.00 0.82 0.00 0.14 0.04 0.00
#&gt; TCGA.SR.A6MV.01     3  0.1814     0.7092 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.SR.A6MP.01     3  0.3797     0.5102 0.00 0.00 0.58 0.00 0.42 0.00
#&gt; TCGA.QR.A70D.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     6  0.2190     0.7696 0.00 0.00 0.04 0.06 0.00 0.90
#&gt; TCGA.WB.A81W.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3  0.2048     0.6961 0.00 0.00 0.88 0.00 0.00 0.12
#&gt; TCGA.WB.A80P.01     2  0.0547     0.9527 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.QT.A5XK.01     5  0.2454     0.7772 0.16 0.00 0.00 0.00 0.84 0.00
#&gt; TCGA.SR.A6MY.01     5  0.3647     0.5578 0.36 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NY.01     5  0.3647     0.5624 0.36 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.WB.A80Y.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WM.01     1  0.3756     0.2746 0.60 0.00 0.00 0.00 0.40 0.00
#&gt; TCGA.QR.A6GR.01     3  0.2941     0.7140 0.00 0.00 0.78 0.00 0.22 0.00
#&gt; TCGA.RW.A686.06     3  0.3198     0.6950 0.00 0.00 0.74 0.00 0.26 0.00
#&gt; TCGA.SR.A6MX.01     2  0.0547     0.9527 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.WB.A822.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70A.01     6  0.2581     0.7478 0.00 0.00 0.12 0.02 0.00 0.86
#&gt; TCGA.RW.A684.01     3  0.1865     0.7089 0.00 0.00 0.92 0.00 0.04 0.04
#&gt; TCGA.SQ.A6I4.01     3  0.1814     0.7092 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.S7.A7WV.01     4  0.0547     0.8210 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.SR.A6MX.05     2  0.0547     0.9527 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.PR.A5PF.01     1  0.4199     0.2949 0.60 0.00 0.00 0.00 0.38 0.02
#&gt; TCGA.W2.A7HC.01     5  0.3045     0.7538 0.10 0.00 0.06 0.00 0.84 0.00
#&gt; TCGA.WB.A81D.01     5  0.2790     0.7743 0.14 0.00 0.02 0.00 0.84 0.00
#&gt; TCGA.WB.A821.01     3  0.1814     0.7092 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.RW.A681.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MZ.01     6  0.3309     0.5826 0.00 0.00 0.28 0.00 0.00 0.72
#&gt; TCGA.RT.A6YA.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WR.01     5  0.3828     0.3367 0.44 0.00 0.00 0.00 0.56 0.00
#&gt; TCGA.RW.A680.01     2  0.0547     0.9527 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.SP.A6QK.01     3  0.3647     0.6058 0.00 0.00 0.64 0.00 0.36 0.00
#&gt; TCGA.SQ.A6I6.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81R.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.2454     0.6915 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.QR.A6H3.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A708.01     6  0.3475     0.7365 0.00 0.00 0.14 0.06 0.00 0.80
#&gt; TCGA.WB.A818.01     1  0.0937     0.8803 0.96 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.SR.A6MX.06     2  0.0547     0.9527 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A703.01     4  0.1267     0.8001 0.00 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.SP.A6QJ.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     5  0.3198     0.7106 0.26 0.00 0.00 0.00 0.74 0.00
#&gt; TCGA.QR.A6H2.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6N0.01     6  0.2350     0.7717 0.00 0.00 0.02 0.10 0.00 0.88
#&gt; TCGA.WB.A820.01     3  0.3797     0.5102 0.00 0.00 0.58 0.00 0.42 0.00
#&gt; TCGA.QR.A6H4.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     6  0.3309     0.7092 0.00 0.00 0.00 0.28 0.00 0.72
#&gt; TCGA.XG.A823.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     5  0.2631     0.6224 0.00 0.00 0.18 0.00 0.82 0.00
#&gt; TCGA.WB.A81Q.01     3  0.3869    -0.1639 0.00 0.00 0.50 0.00 0.00 0.50
#&gt; TCGA.WB.A81G.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A814.01     4  0.1267     0.8001 0.00 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     3  0.4892     0.3638 0.00 0.00 0.50 0.00 0.44 0.06
#&gt; TCGA.WB.A819.01     5  0.2631     0.6224 0.00 0.00 0.18 0.00 0.82 0.00
#&gt; TCGA.QR.A70H.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PG.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     4  0.2941     0.6657 0.00 0.00 0.00 0.78 0.00 0.22
#&gt; TCGA.P8.A6RY.01     4  0.1092     0.8196 0.00 0.00 0.00 0.96 0.02 0.02
#&gt; TCGA.QR.A70Q.01     2  0.3997     0.8144 0.00 0.78 0.02 0.14 0.06 0.00
#&gt; TCGA.RT.A6YC.01     1  0.0937     0.8803 0.96 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.SR.A6MR.01     6  0.2512     0.7691 0.00 0.00 0.06 0.06 0.00 0.88
#&gt; TCGA.S7.A7WL.01     3  0.3982     0.6729 0.00 0.00 0.74 0.00 0.20 0.06
#&gt; TCGA.WB.A80M.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81S.01     5  0.3578     0.6016 0.34 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.S7.A7X0.01     6  0.3409     0.6743 0.00 0.00 0.00 0.30 0.00 0.70
#&gt; TCGA.SP.A6QG.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70W.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A817.01     6  0.3828     0.3150 0.00 0.00 0.44 0.00 0.00 0.56
#&gt; TCGA.RW.A7D0.01     3  0.3828     0.4934 0.00 0.00 0.56 0.00 0.44 0.00
#&gt; TCGA.TT.A6YK.01     6  0.3309     0.7092 0.00 0.00 0.00 0.28 0.00 0.72
#&gt; TCGA.SP.A6QD.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     3  0.2048     0.6961 0.00 0.00 0.88 0.00 0.00 0.12
#&gt; TCGA.SR.A6MQ.01     3  0.1807     0.6988 0.00 0.00 0.92 0.00 0.02 0.06
#&gt; TCGA.QR.A70N.01     6  0.3198     0.7219 0.00 0.00 0.00 0.26 0.00 0.74
#&gt; TCGA.QR.A6GT.01     2  0.0547     0.9527 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A70P.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A685.01     5  0.2631     0.6224 0.00 0.00 0.18 0.00 0.82 0.00
#&gt; TCGA.QR.A70I.01     4  0.3076     0.6224 0.00 0.24 0.00 0.76 0.00 0.00
#&gt; TCGA.QR.A70K.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QC.01     5  0.3756    -0.0337 0.00 0.00 0.40 0.00 0.60 0.00
#&gt; TCGA.S7.A7WP.01     4  0.3309     0.5478 0.00 0.28 0.00 0.72 0.00 0.00
#&gt; TCGA.WB.A81T.01     5  0.2454     0.6450 0.00 0.00 0.16 0.00 0.84 0.00
#&gt; TCGA.QR.A70J.01     4  0.0000     0.8199 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7X2.01     5  0.2454     0.7772 0.16 0.00 0.00 0.00 0.84 0.00
#&gt; TCGA.W2.A7HB.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     4  0.2941     0.6657 0.00 0.00 0.00 0.78 0.00 0.22
#&gt; TCGA.QR.A70G.01     3  0.1814     0.7092 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.QR.A6H5.01     4  0.2941     0.6657 0.00 0.00 0.00 0.78 0.00 0.22
#&gt; TCGA.WB.A81V.01     3  0.3797     0.5102 0.00 0.00 0.58 0.00 0.42 0.00
#&gt; TCGA.SP.A6QI.01     5  0.3746     0.7541 0.14 0.00 0.08 0.00 0.78 0.00
#&gt; TCGA.SA.A6C2.01     4  0.1092     0.8196 0.00 0.00 0.00 0.96 0.02 0.02
#&gt; TCGA.RW.A68B.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MT.01     4  0.1092     0.8196 0.00 0.00 0.00 0.96 0.02 0.02
#&gt; TCGA.RW.A67W.01     1  0.3756     0.2746 0.60 0.00 0.00 0.00 0.40 0.00
#&gt; TCGA.RW.A68G.01     5  0.3578     0.6016 0.34 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.TT.A6YO.01     2  0.3163     0.8471 0.00 0.82 0.00 0.14 0.04 0.00
#&gt; TCGA.QT.A69Q.01     5  0.3578     0.6016 0.34 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.RM.A68T.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     5  0.3746     0.7541 0.14 0.00 0.08 0.00 0.78 0.00
#&gt; TCGA.QR.A6GS.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81E.01     4  0.3324     0.7529 0.00 0.08 0.02 0.84 0.06 0.00
#&gt; TCGA.QR.A6GU.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HA.01     5  0.2454     0.7772 0.16 0.00 0.00 0.00 0.84 0.00
#&gt; TCGA.RW.A67V.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81N.01     3  0.2793     0.7059 0.00 0.00 0.80 0.00 0.20 0.00
#&gt; TCGA.WB.A80O.01     5  0.2454     0.6450 0.00 0.00 0.16 0.00 0.84 0.00
#&gt; TCGA.QT.A5XN.01     3  0.4845     0.4565 0.00 0.00 0.54 0.00 0.40 0.06
#&gt; TCGA.QR.A70M.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WW.01     6  0.2941     0.7332 0.00 0.00 0.00 0.22 0.00 0.78
#&gt; TCGA.WB.A816.01     3  0.1814     0.7092 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.QR.A70T.01     6  0.3324     0.7674 0.00 0.00 0.06 0.08 0.02 0.84
#&gt; TCGA.RW.A68F.01     2  0.0000     0.9569 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A705.01     2  0.0547     0.9510 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.P7.A5NY.05     3  0.2793     0.6185 0.00 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.SP.A6QF.01     5  0.3309     0.6846 0.28 0.00 0.00 0.00 0.72 0.00
#&gt; TCGA.QR.A707.01     1  0.3578     0.4346 0.66 0.00 0.00 0.00 0.34 0.00
#&gt; TCGA.S7.A7WO.01     2  0.3163     0.8471 0.00 0.82 0.00 0.14 0.04 0.00
#&gt; TCGA.W2.A7H5.01     3  0.3706     0.5218 0.00 0.00 0.62 0.00 0.38 0.00
#&gt; TCGA.QT.A5XO.01     1  0.3706     0.3332 0.62 0.00 0.00 0.00 0.38 0.00
#&gt; TCGA.QR.A6GW.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A815.01     5  0.3073     0.7375 0.08 0.00 0.08 0.00 0.84 0.00
#&gt; TCGA.QR.A6ZZ.01     4  0.3309     0.5478 0.00 0.28 0.00 0.72 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     3  0.2941     0.7172 0.00 0.00 0.78 0.00 0.22 0.00
#&gt; TCGA.QR.A6H1.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YN.01     1  0.3756     0.2746 0.60 0.00 0.00 0.00 0.40 0.00
#&gt; TCGA.P7.A5NX.01     2  0.2048     0.8828 0.00 0.88 0.00 0.12 0.00 0.00
#&gt; TCGA.WB.A81J.01     1  0.3198     0.5988 0.74 0.00 0.00 0.00 0.26 0.00
#&gt; TCGA.RW.A686.01     3  0.3076     0.7083 0.00 0.00 0.76 0.00 0.24 0.00
#&gt; TCGA.WB.A81I.01     5  0.3156     0.6089 0.00 0.00 0.18 0.00 0.80 0.02
#&gt; TCGA.QT.A5XP.01     5  0.2956     0.7661 0.12 0.00 0.04 0.00 0.84 0.00
#&gt; TCGA.RW.A8AZ.01     5  0.3156     0.7727 0.18 0.00 0.00 0.00 0.80 0.02
#&gt; TCGA.W2.A7HE.01     3  0.2631     0.6462 0.00 0.00 0.82 0.00 0.00 0.18
#&gt; TCGA.P8.A5KC.01     6  0.3309     0.7092 0.00 0.00 0.00 0.28 0.00 0.72
#&gt; TCGA.QR.A6GX.01     6  0.2048     0.7640 0.00 0.00 0.00 0.12 0.00 0.88
#&gt; TCGA.P8.A6RX.01     2  0.0937     0.9390 0.00 0.96 0.00 0.04 0.00 0.00
#&gt; TCGA.QT.A5XL.01     4  0.2260     0.7524 0.00 0.00 0.00 0.86 0.00 0.14
#&gt; TCGA.WB.A81A.01     6  0.2631     0.6829 0.00 0.00 0.18 0.00 0.00 0.82
#&gt; TCGA.QR.A70E.01     6  0.2190     0.7696 0.00 0.00 0.04 0.06 0.00 0.90
#&gt; TCGA.QR.A702.01     5  0.3982     0.5448 0.00 0.00 0.20 0.00 0.74 0.06
#&gt; TCGA.S7.A7WN.01     3  0.3828     0.4934 0.00 0.00 0.56 0.00 0.44 0.00
#&gt; TCGA.QR.A6GO.01     1  0.1556     0.8452 0.92 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.SR.A6MS.01     1  0.2260     0.7815 0.86 0.00 0.00 0.00 0.14 0.00
#&gt; TCGA.SR.A6MU.01     6  0.3578     0.4722 0.00 0.00 0.34 0.00 0.00 0.66
#&gt; TCGA.QR.A70R.01     1  0.0547     0.8943 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A6GY.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.0000     0.9069 1.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-5-a').parent().next().next().hide();
$('#tab-node-0-get-classes-5-a').click(function(){
  $('#tab-node-0-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-6'>
<p><a id='tab-node-0-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.QR.A6H6.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.01     4  0.0000     0.8343 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81K.01     5  0.3770     0.3676 0.00 0.00 0.18 0.00 0.74 0.00 0.08
#&gt; TCGA.RW.A68D.01     4  0.1671     0.8200 0.00 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.RT.A6Y9.01     4  0.1671     0.8200 0.00 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.QR.A7IN.01     6  0.3745     0.6823 0.00 0.00 0.00 0.26 0.00 0.70 0.04
#&gt; TCGA.QR.A7IP.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80N.01     1  0.3047     0.5861 0.72 0.00 0.00 0.00 0.28 0.00 0.00
#&gt; TCGA.QR.A6H0.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A689.01     1  0.0504     0.9285 0.98 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.P8.A5KC.11     2  0.2081     0.8904 0.00 0.86 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.QR.A70O.01     7  0.5888     0.8787 0.00 0.00 0.36 0.00 0.22 0.02 0.40
#&gt; TCGA.QR.A700.01     3  0.4615     0.2824 0.00 0.00 0.60 0.00 0.00 0.30 0.10
#&gt; TCGA.SQ.A6I4.11     2  0.2081     0.8904 0.00 0.86 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.QR.A70C.01     3  0.1363     0.5960 0.00 0.00 0.94 0.00 0.00 0.04 0.02
#&gt; TCGA.WB.A80L.01     3  0.1928     0.5595 0.00 0.00 0.90 0.00 0.08 0.00 0.02
#&gt; TCGA.WB.A81P.01     3  0.3058     0.4776 0.00 0.00 0.82 0.00 0.08 0.00 0.10
#&gt; TCGA.S7.A7X1.01     4  0.4328     0.2669 0.00 0.00 0.00 0.60 0.00 0.34 0.06
#&gt; TCGA.QT.A7U0.01     6  0.3745     0.6823 0.00 0.00 0.00 0.26 0.00 0.70 0.04
#&gt; TCGA.WB.A81M.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68A.01     3  0.3487     0.5105 0.00 0.00 0.78 0.00 0.00 0.12 0.10
#&gt; TCGA.RW.A68C.01     4  0.2313     0.8046 0.00 0.00 0.00 0.88 0.00 0.06 0.06
#&gt; TCGA.TT.A6YP.01     4  0.2313     0.8046 0.00 0.00 0.00 0.88 0.00 0.06 0.06
#&gt; TCGA.RW.A67X.01     4  0.2313     0.8046 0.00 0.00 0.00 0.88 0.00 0.06 0.06
#&gt; TCGA.RW.A688.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HF.01     5  0.3011     0.7162 0.12 0.00 0.00 0.00 0.82 0.00 0.06
#&gt; TCGA.WB.A80K.01     3  0.1928     0.5595 0.00 0.00 0.90 0.00 0.08 0.00 0.02
#&gt; TCGA.QT.A5XM.01     3  0.4418    -0.0275 0.00 0.00 0.62 0.00 0.30 0.00 0.08
#&gt; TCGA.S7.A7WT.01     5  0.1664     0.6848 0.02 0.00 0.06 0.00 0.92 0.00 0.00
#&gt; TCGA.SP.A6QH.01     4  0.0504     0.8351 0.00 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.QR.A706.01     6  0.4015     0.6597 0.00 0.00 0.00 0.26 0.00 0.68 0.06
#&gt; TCGA.RM.A68W.01     2  0.0504     0.9603 0.00 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.S7.A7WX.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80V.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70X.01     3  0.0504     0.5891 0.00 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.W2.A7HD.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70V.01     5  0.4003     0.3862 0.04 0.00 0.00 0.00 0.64 0.00 0.32
#&gt; TCGA.WB.A81H.01     3  0.1363     0.5960 0.00 0.00 0.94 0.00 0.00 0.04 0.02
#&gt; TCGA.QT.A5XJ.01     4  0.1886     0.8127 0.00 0.00 0.00 0.88 0.00 0.00 0.12
#&gt; TCGA.P8.A5KD.11     2  0.2081     0.8904 0.00 0.86 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.SR.A6MV.01     3  0.1363     0.5960 0.00 0.00 0.94 0.00 0.00 0.04 0.02
#&gt; TCGA.SR.A6MP.01     3  0.4714    -0.0939 0.00 0.00 0.60 0.00 0.28 0.00 0.12
#&gt; TCGA.QR.A70D.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     6  0.2421     0.7441 0.00 0.00 0.08 0.00 0.02 0.88 0.02
#&gt; TCGA.WB.A81W.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3  0.2512     0.5521 0.00 0.00 0.86 0.00 0.00 0.10 0.04
#&gt; TCGA.WB.A80P.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XK.01     5  0.1433     0.7217 0.08 0.00 0.00 0.00 0.92 0.00 0.00
#&gt; TCGA.SR.A6MY.01     5  0.2259     0.7157 0.16 0.00 0.00 0.00 0.84 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NY.01     5  0.3199     0.7100 0.14 0.00 0.00 0.00 0.80 0.00 0.06
#&gt; TCGA.WB.A80Y.01     1  0.0504     0.9285 0.98 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.S7.A7WM.01     5  0.3815     0.4870 0.36 0.00 0.00 0.00 0.62 0.00 0.02
#&gt; TCGA.QR.A6GR.01     3  0.3058     0.4776 0.00 0.00 0.82 0.00 0.08 0.00 0.10
#&gt; TCGA.RW.A686.06     3  0.1928     0.5595 0.00 0.00 0.90 0.00 0.08 0.00 0.02
#&gt; TCGA.SR.A6MX.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A822.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70A.01     6  0.3927     0.7035 0.00 0.00 0.14 0.00 0.02 0.76 0.08
#&gt; TCGA.RW.A684.01     3  0.4937     0.3588 0.00 0.00 0.68 0.00 0.06 0.12 0.14
#&gt; TCGA.SQ.A6I4.01     3  0.1363     0.5960 0.00 0.00 0.94 0.00 0.00 0.04 0.02
#&gt; TCGA.S7.A7WV.01     4  0.0504     0.8351 0.00 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.SR.A6MX.05     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PF.01     5  0.4960     0.5361 0.30 0.00 0.00 0.00 0.60 0.04 0.06
#&gt; TCGA.W2.A7HC.01     5  0.2159     0.6710 0.02 0.00 0.06 0.00 0.90 0.00 0.02
#&gt; TCGA.WB.A81D.01     5  0.2159     0.6710 0.02 0.00 0.06 0.00 0.90 0.00 0.02
#&gt; TCGA.WB.A821.01     3  0.1363     0.5960 0.00 0.00 0.94 0.00 0.00 0.04 0.02
#&gt; TCGA.RW.A681.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MZ.01     6  0.4779     0.6515 0.00 0.00 0.18 0.00 0.04 0.68 0.10
#&gt; TCGA.RT.A6YA.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WR.01     5  0.2572     0.6909 0.20 0.00 0.00 0.00 0.80 0.00 0.00
#&gt; TCGA.RW.A680.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     3  0.3770     0.3315 0.00 0.00 0.74 0.00 0.18 0.00 0.08
#&gt; TCGA.SQ.A6I6.01     1  0.0504     0.9285 0.98 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.WB.A81R.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.2769     0.5697 0.00 0.00 0.86 0.00 0.02 0.08 0.04
#&gt; TCGA.QR.A6H3.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A708.01     6  0.4162     0.6861 0.00 0.00 0.12 0.00 0.02 0.74 0.12
#&gt; TCGA.WB.A818.01     1  0.2422     0.7559 0.82 0.00 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.SR.A6MX.06     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A703.01     4  0.0863     0.8247 0.00 0.04 0.00 0.96 0.00 0.00 0.00
#&gt; TCGA.SP.A6QJ.01     1  0.0504     0.9285 0.98 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.P8.A5KD.01     5  0.2163     0.7254 0.10 0.00 0.00 0.00 0.88 0.00 0.02
#&gt; TCGA.QR.A6H2.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6N0.01     6  0.4022     0.7448 0.00 0.00 0.02 0.10 0.02 0.78 0.08
#&gt; TCGA.WB.A820.01     3  0.4615    -0.0824 0.00 0.00 0.60 0.00 0.30 0.00 0.10
#&gt; TCGA.QR.A6H4.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     6  0.3745     0.6823 0.00 0.00 0.00 0.26 0.00 0.70 0.04
#&gt; TCGA.XG.A823.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     5  0.3985     0.3336 0.00 0.00 0.18 0.00 0.72 0.00 0.10
#&gt; TCGA.WB.A81Q.01     6  0.4850     0.3709 0.00 0.00 0.32 0.00 0.00 0.56 0.12
#&gt; TCGA.WB.A81G.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A814.01     4  0.0863     0.8247 0.00 0.04 0.00 0.96 0.00 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     7  0.5973     0.8624 0.00 0.00 0.30 0.00 0.28 0.02 0.40
#&gt; TCGA.WB.A819.01     5  0.3526     0.4122 0.00 0.00 0.18 0.00 0.76 0.00 0.06
#&gt; TCGA.QR.A70H.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PG.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     4  0.2803     0.7716 0.00 0.00 0.00 0.84 0.00 0.10 0.06
#&gt; TCGA.P8.A6RY.01     4  0.1671     0.8200 0.00 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.QR.A70Q.01     2  0.4030     0.7197 0.00 0.72 0.00 0.12 0.00 0.00 0.16
#&gt; TCGA.RT.A6YC.01     1  0.2422     0.7559 0.82 0.00 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.SR.A6MR.01     6  0.3257     0.7486 0.00 0.00 0.02 0.04 0.02 0.84 0.08
#&gt; TCGA.S7.A7WL.01     3  0.4569     0.1373 0.00 0.00 0.64 0.00 0.06 0.02 0.28
#&gt; TCGA.WB.A80M.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81S.01     5  0.2745     0.7116 0.16 0.00 0.00 0.00 0.82 0.00 0.02
#&gt; TCGA.S7.A7X0.01     6  0.4015     0.6597 0.00 0.00 0.00 0.26 0.00 0.68 0.06
#&gt; TCGA.SP.A6QG.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70W.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A817.01     6  0.4828     0.4628 0.00 0.00 0.36 0.00 0.02 0.56 0.06
#&gt; TCGA.RW.A7D0.01     3  0.4487    -0.0882 0.00 0.00 0.60 0.00 0.32 0.00 0.08
#&gt; TCGA.TT.A6YK.01     6  0.3417     0.6844 0.00 0.00 0.00 0.26 0.00 0.72 0.02
#&gt; TCGA.SP.A6QD.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     3  0.2313     0.5666 0.00 0.00 0.88 0.00 0.00 0.06 0.06
#&gt; TCGA.SR.A6MQ.01     3  0.4667     0.3632 0.00 0.00 0.70 0.00 0.04 0.12 0.14
#&gt; TCGA.QR.A70N.01     6  0.3911     0.6804 0.00 0.00 0.00 0.24 0.00 0.70 0.06
#&gt; TCGA.QR.A6GT.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70P.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A685.01     5  0.3770     0.3676 0.00 0.00 0.18 0.00 0.74 0.00 0.08
#&gt; TCGA.QR.A70I.01     4  0.4248     0.5698 0.00 0.26 0.00 0.66 0.00 0.00 0.08
#&gt; TCGA.QR.A70K.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QC.01     3  0.4692    -0.3166 0.00 0.00 0.50 0.00 0.42 0.00 0.08
#&gt; TCGA.S7.A7WP.01     4  0.2945     0.5988 0.00 0.26 0.00 0.74 0.00 0.00 0.00
#&gt; TCGA.WB.A81T.01     5  0.1928     0.6406 0.00 0.00 0.08 0.00 0.90 0.00 0.02
#&gt; TCGA.QR.A70J.01     4  0.0504     0.8351 0.00 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.S7.A7X2.01     5  0.1433     0.7217 0.08 0.00 0.00 0.00 0.92 0.00 0.00
#&gt; TCGA.W2.A7HB.01     1  0.0504     0.9285 0.98 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.W2.A7UY.01     4  0.2803     0.7716 0.00 0.00 0.00 0.84 0.00 0.10 0.06
#&gt; TCGA.QR.A70G.01     3  0.1006     0.5971 0.00 0.00 0.96 0.00 0.00 0.02 0.02
#&gt; TCGA.QR.A6H5.01     4  0.2803     0.7716 0.00 0.00 0.00 0.84 0.00 0.10 0.06
#&gt; TCGA.WB.A81V.01     3  0.4714    -0.0939 0.00 0.00 0.60 0.00 0.28 0.00 0.12
#&gt; TCGA.SP.A6QI.01     5  0.3244     0.5821 0.04 0.00 0.00 0.00 0.78 0.00 0.18
#&gt; TCGA.SA.A6C2.01     4  0.1166     0.8289 0.00 0.00 0.00 0.94 0.00 0.00 0.06
#&gt; TCGA.RW.A68B.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MT.01     4  0.1671     0.8200 0.00 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.RW.A67W.01     5  0.3685     0.5614 0.32 0.00 0.00 0.00 0.66 0.00 0.02
#&gt; TCGA.RW.A68G.01     5  0.2259     0.7157 0.16 0.00 0.00 0.00 0.84 0.00 0.00
#&gt; TCGA.TT.A6YO.01     2  0.2081     0.8904 0.00 0.86 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.QT.A69Q.01     5  0.2569     0.7208 0.14 0.00 0.00 0.00 0.84 0.00 0.02
#&gt; TCGA.RM.A68T.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     5  0.3244     0.5821 0.04 0.00 0.00 0.00 0.78 0.00 0.18
#&gt; TCGA.QR.A6GS.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81E.01     4  0.2572     0.7614 0.00 0.00 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.QR.A6GU.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HA.01     5  0.1433     0.7217 0.08 0.00 0.00 0.00 0.92 0.00 0.00
#&gt; TCGA.RW.A67V.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81N.01     3  0.3908     0.3553 0.00 0.00 0.72 0.00 0.08 0.00 0.20
#&gt; TCGA.WB.A80O.01     5  0.1928     0.6406 0.00 0.00 0.08 0.00 0.90 0.00 0.02
#&gt; TCGA.QT.A5XN.01     7  0.5931     0.9077 0.00 0.00 0.34 0.00 0.24 0.02 0.40
#&gt; TCGA.QR.A70M.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WW.01     6  0.3985     0.7053 0.00 0.00 0.00 0.18 0.00 0.72 0.10
#&gt; TCGA.WB.A816.01     3  0.0504     0.5964 0.00 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A70T.01     6  0.4357     0.7417 0.00 0.00 0.04 0.08 0.02 0.76 0.10
#&gt; TCGA.RW.A68F.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A705.01     2  0.0863     0.9513 0.00 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.P7.A5NY.05     3  0.4707     0.3724 0.00 0.00 0.66 0.00 0.02 0.22 0.10
#&gt; TCGA.SP.A6QF.01     5  0.1886     0.7256 0.12 0.00 0.00 0.00 0.88 0.00 0.00
#&gt; TCGA.QR.A707.01     5  0.4266     0.2795 0.44 0.00 0.00 0.00 0.52 0.00 0.04
#&gt; TCGA.S7.A7WO.01     2  0.2081     0.8904 0.00 0.86 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.W2.A7H5.01     3  0.5560    -0.6816 0.00 0.00 0.42 0.00 0.28 0.00 0.30
#&gt; TCGA.QT.A5XO.01     5  0.3867     0.4449 0.38 0.00 0.00 0.00 0.60 0.00 0.02
#&gt; TCGA.QR.A6GW.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A815.01     5  0.1664     0.6848 0.02 0.00 0.06 0.00 0.92 0.00 0.00
#&gt; TCGA.QR.A6ZZ.01     4  0.2945     0.5988 0.00 0.26 0.00 0.74 0.00 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     3  0.2572     0.5226 0.00 0.00 0.86 0.00 0.08 0.00 0.06
#&gt; TCGA.QR.A6H1.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YN.01     5  0.4127     0.4775 0.36 0.00 0.00 0.00 0.60 0.00 0.04
#&gt; TCGA.P7.A5NX.01     2  0.1363     0.9273 0.00 0.94 0.00 0.04 0.00 0.00 0.02
#&gt; TCGA.WB.A81J.01     1  0.4266    -0.0255 0.52 0.00 0.00 0.00 0.44 0.00 0.04
#&gt; TCGA.RW.A686.01     3  0.1928     0.5595 0.00 0.00 0.90 0.00 0.08 0.00 0.02
#&gt; TCGA.WB.A81I.01     5  0.5304     0.1938 0.00 0.00 0.24 0.00 0.60 0.04 0.12
#&gt; TCGA.QT.A5XP.01     5  0.1664     0.6848 0.02 0.00 0.06 0.00 0.92 0.00 0.00
#&gt; TCGA.RW.A8AZ.01     5  0.3404     0.6999 0.08 0.00 0.00 0.00 0.82 0.04 0.06
#&gt; TCGA.W2.A7HE.01     3  0.3991     0.4234 0.00 0.00 0.72 0.00 0.02 0.22 0.04
#&gt; TCGA.P8.A5KC.01     6  0.4015     0.6597 0.00 0.00 0.00 0.26 0.00 0.68 0.06
#&gt; TCGA.QR.A6GX.01     6  0.3054     0.7487 0.00 0.00 0.04 0.04 0.02 0.86 0.04
#&gt; TCGA.P8.A6RX.01     2  0.0000     0.9696 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XL.01     4  0.2313     0.8046 0.00 0.00 0.00 0.88 0.00 0.06 0.06
#&gt; TCGA.WB.A81A.01     6  0.4298     0.6855 0.00 0.00 0.12 0.00 0.04 0.74 0.10
#&gt; TCGA.QR.A70E.01     6  0.3600     0.7431 0.00 0.00 0.02 0.04 0.04 0.82 0.08
#&gt; TCGA.QR.A702.01     5  0.4902    -0.1876 0.00 0.00 0.12 0.00 0.54 0.00 0.34
#&gt; TCGA.S7.A7WN.01     3  0.4615    -0.0824 0.00 0.00 0.60 0.00 0.30 0.00 0.10
#&gt; TCGA.QR.A6GO.01     1  0.2832     0.6601 0.76 0.00 0.00 0.00 0.24 0.00 0.00
#&gt; TCGA.SR.A6MS.01     1  0.3139     0.5407 0.70 0.00 0.00 0.00 0.30 0.00 0.00
#&gt; TCGA.SR.A6MU.01     6  0.4779     0.6515 0.00 0.00 0.18 0.00 0.04 0.68 0.10
#&gt; TCGA.QR.A70R.01     1  0.0863     0.9128 0.96 0.00 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.QR.A6GY.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.0000     0.9388 1.00 0.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-6-a').parent().next().next().hide();
$('#tab-node-0-get-classes-6-a').click(function(){
  $('#tab-node-0-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-7'>
<p><a id='tab-node-0-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.QR.A6H6.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.01     4  0.0000     0.8255 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81K.01     5  0.3449     0.3587 0.00 0.00 0.32 0.00 0.66 0.00 0.00 0.02
#&gt; TCGA.RW.A68D.01     4  0.1563     0.8172 0.00 0.00 0.00 0.90 0.00 0.00 0.10 0.00
#&gt; TCGA.RT.A6Y9.01     4  0.1765     0.8138 0.00 0.00 0.00 0.88 0.00 0.00 0.12 0.00
#&gt; TCGA.QR.A7IN.01     6  0.1804     0.7439 0.00 0.00 0.00 0.08 0.00 0.90 0.00 0.02
#&gt; TCGA.QR.A7IP.01     2  0.0471     0.9218 0.00 0.98 0.00 0.02 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80N.01     5  0.3329     0.0916 0.48 0.00 0.00 0.00 0.52 0.00 0.00 0.00
#&gt; TCGA.QR.A6H0.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A689.01     1  0.1091     0.8979 0.94 0.00 0.00 0.00 0.06 0.00 0.00 0.00
#&gt; TCGA.P8.A5KC.11     2  0.4202     0.7731 0.00 0.74 0.00 0.14 0.02 0.00 0.06 0.04
#&gt; TCGA.QR.A70O.01     7  0.5273     0.6006 0.00 0.00 0.42 0.00 0.06 0.00 0.44 0.08
#&gt; TCGA.QR.A700.01     8  0.4077     0.4936 0.00 0.00 0.40 0.00 0.00 0.02 0.02 0.56
#&gt; TCGA.SQ.A6I4.11     2  0.4202     0.7731 0.00 0.74 0.00 0.14 0.02 0.00 0.06 0.04
#&gt; TCGA.QR.A70C.01     3  0.3237     0.0398 0.00 0.00 0.60 0.00 0.00 0.00 0.00 0.40
#&gt; TCGA.WB.A80L.01     3  0.2856     0.4289 0.00 0.00 0.78 0.00 0.02 0.00 0.00 0.20
#&gt; TCGA.WB.A81P.01     3  0.0471     0.4833 0.00 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.S7.A7X1.01     6  0.2852     0.3988 0.00 0.00 0.00 0.28 0.00 0.72 0.00 0.00
#&gt; TCGA.QT.A7U0.01     6  0.1804     0.7439 0.00 0.00 0.00 0.08 0.00 0.90 0.00 0.02
#&gt; TCGA.WB.A81M.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68A.01     3  0.4137    -0.3426 0.00 0.00 0.50 0.00 0.00 0.02 0.02 0.46
#&gt; TCGA.RW.A68C.01     4  0.3083     0.6587 0.00 0.00 0.00 0.66 0.00 0.34 0.00 0.00
#&gt; TCGA.TT.A6YP.01     4  0.3015     0.6751 0.00 0.00 0.00 0.68 0.00 0.32 0.00 0.00
#&gt; TCGA.RW.A67X.01     4  0.3142     0.6368 0.00 0.00 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.RW.A688.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HF.01     5  0.2914     0.7239 0.08 0.00 0.00 0.00 0.84 0.00 0.04 0.04
#&gt; TCGA.WB.A80K.01     3  0.2856     0.4289 0.00 0.00 0.78 0.00 0.02 0.00 0.00 0.20
#&gt; TCGA.QT.A5XM.01     3  0.2404     0.3603 0.00 0.00 0.84 0.00 0.14 0.00 0.00 0.02
#&gt; TCGA.S7.A7WT.01     5  0.2025     0.6940 0.00 0.00 0.10 0.00 0.88 0.00 0.00 0.02
#&gt; TCGA.SP.A6QH.01     4  0.0808     0.8227 0.00 0.00 0.00 0.96 0.00 0.04 0.00 0.00
#&gt; TCGA.QR.A706.01     6  0.1341     0.7393 0.00 0.00 0.00 0.08 0.00 0.92 0.00 0.00
#&gt; TCGA.RM.A68W.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WX.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80V.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70X.01     3  0.2852     0.3108 0.00 0.00 0.72 0.00 0.00 0.00 0.00 0.28
#&gt; TCGA.W2.A7HD.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70V.01     7  0.3729     0.0967 0.00 0.00 0.02 0.00 0.46 0.00 0.52 0.00
#&gt; TCGA.WB.A81H.01     3  0.3193     0.0917 0.00 0.00 0.62 0.00 0.00 0.00 0.00 0.38
#&gt; TCGA.QT.A5XJ.01     4  0.1341     0.8187 0.00 0.00 0.00 0.92 0.00 0.00 0.08 0.00
#&gt; TCGA.P8.A5KD.11     2  0.4202     0.7731 0.00 0.74 0.00 0.14 0.02 0.00 0.06 0.04
#&gt; TCGA.SR.A6MV.01     3  0.3237     0.0212 0.00 0.00 0.60 0.00 0.00 0.00 0.00 0.40
#&gt; TCGA.SR.A6MP.01     3  0.2132     0.4008 0.00 0.00 0.88 0.00 0.08 0.00 0.04 0.00
#&gt; TCGA.QR.A70D.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     6  0.2725     0.7149 0.00 0.00 0.00 0.00 0.00 0.82 0.04 0.14
#&gt; TCGA.WB.A81W.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3  0.3729    -0.2270 0.00 0.00 0.52 0.00 0.00 0.02 0.00 0.46
#&gt; TCGA.WB.A80P.01     2  0.0471     0.9269 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.QT.A5XK.01     5  0.1557     0.7450 0.06 0.00 0.00 0.00 0.92 0.00 0.00 0.02
#&gt; TCGA.SR.A6MY.01     5  0.1341     0.7474 0.08 0.00 0.00 0.00 0.92 0.00 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NY.01     5  0.3185     0.6780 0.04 0.00 0.00 0.00 0.82 0.00 0.06 0.08
#&gt; TCGA.WB.A80Y.01     1  0.1091     0.8979 0.94 0.00 0.00 0.00 0.06 0.00 0.00 0.00
#&gt; TCGA.S7.A7WM.01     5  0.2404     0.7078 0.14 0.00 0.00 0.00 0.84 0.00 0.00 0.02
#&gt; TCGA.QR.A6GR.01     3  0.1741     0.4762 0.00 0.00 0.92 0.00 0.02 0.00 0.04 0.02
#&gt; TCGA.RW.A686.06     3  0.2719     0.4354 0.00 0.00 0.80 0.00 0.02 0.00 0.00 0.18
#&gt; TCGA.SR.A6MX.01     2  0.0471     0.9269 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.WB.A822.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70A.01     6  0.4406     0.6246 0.00 0.00 0.02 0.00 0.00 0.64 0.08 0.26
#&gt; TCGA.RW.A684.01     3  0.4885     0.1207 0.00 0.00 0.60 0.00 0.00 0.04 0.10 0.26
#&gt; TCGA.SQ.A6I4.01     3  0.3015     0.2445 0.00 0.00 0.68 0.00 0.00 0.00 0.00 0.32
#&gt; TCGA.S7.A7WV.01     4  0.1563     0.8110 0.00 0.00 0.00 0.90 0.00 0.10 0.00 0.00
#&gt; TCGA.SR.A6MX.05     2  0.0471     0.9269 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.PR.A5PF.01     5  0.3710     0.6499 0.12 0.00 0.00 0.00 0.76 0.00 0.02 0.10
#&gt; TCGA.W2.A7HC.01     5  0.2025     0.6940 0.00 0.00 0.10 0.00 0.88 0.00 0.00 0.02
#&gt; TCGA.WB.A81D.01     5  0.2025     0.6940 0.00 0.00 0.10 0.00 0.88 0.00 0.00 0.02
#&gt; TCGA.WB.A821.01     3  0.3237     0.0212 0.00 0.00 0.60 0.00 0.00 0.00 0.00 0.40
#&gt; TCGA.RW.A681.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MZ.01     6  0.5089     0.4641 0.00 0.00 0.02 0.00 0.00 0.52 0.14 0.32
#&gt; TCGA.RT.A6YA.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WR.01     5  0.1341     0.7474 0.08 0.00 0.00 0.00 0.92 0.00 0.00 0.00
#&gt; TCGA.RW.A680.01     2  0.0471     0.9269 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.SP.A6QK.01     3  0.1275     0.4871 0.00 0.00 0.94 0.00 0.04 0.00 0.00 0.02
#&gt; TCGA.SQ.A6I6.01     1  0.1091     0.8979 0.94 0.00 0.00 0.00 0.06 0.00 0.00 0.00
#&gt; TCGA.WB.A81R.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.4518    -0.0023 0.00 0.00 0.56 0.00 0.00 0.02 0.06 0.36
#&gt; TCGA.QR.A6H3.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A708.01     6  0.5032     0.5364 0.00 0.00 0.02 0.00 0.00 0.56 0.16 0.26
#&gt; TCGA.WB.A818.01     1  0.2852     0.6019 0.72 0.00 0.00 0.00 0.28 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.06     2  0.0471     0.9269 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A703.01     4  0.0000     0.8255 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QJ.01     1  0.1091     0.8979 0.94 0.00 0.00 0.00 0.06 0.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     5  0.1557     0.7456 0.06 0.00 0.00 0.00 0.92 0.00 0.00 0.02
#&gt; TCGA.QR.A6H2.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6N0.01     6  0.3657     0.6946 0.00 0.00 0.00 0.00 0.00 0.72 0.08 0.20
#&gt; TCGA.WB.A820.01     3  0.2350     0.3741 0.00 0.00 0.86 0.00 0.10 0.00 0.04 0.00
#&gt; TCGA.QR.A6H4.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     6  0.2265     0.7465 0.00 0.00 0.00 0.08 0.00 0.88 0.02 0.02
#&gt; TCGA.XG.A823.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     3  0.4141    -0.2757 0.00 0.00 0.48 0.00 0.48 0.00 0.02 0.02
#&gt; TCGA.WB.A81Q.01     8  0.5032     0.5877 0.00 0.00 0.26 0.00 0.00 0.16 0.02 0.56
#&gt; TCGA.WB.A81G.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A814.01     4  0.0000     0.8255 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     7  0.4537     0.6652 0.00 0.00 0.40 0.00 0.10 0.00 0.50 0.00
#&gt; TCGA.WB.A819.01     5  0.3291     0.4458 0.00 0.00 0.28 0.00 0.70 0.00 0.00 0.02
#&gt; TCGA.QR.A70H.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.PR.A5PG.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     4  0.3142     0.6368 0.00 0.00 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.P8.A6RY.01     4  0.2547     0.8120 0.00 0.00 0.00 0.84 0.00 0.04 0.12 0.00
#&gt; TCGA.QR.A70Q.01     2  0.3514     0.5873 0.00 0.64 0.00 0.34 0.00 0.00 0.02 0.00
#&gt; TCGA.RT.A6YC.01     1  0.2852     0.6019 0.72 0.00 0.00 0.00 0.28 0.00 0.00 0.00
#&gt; TCGA.SR.A6MR.01     6  0.3774     0.6879 0.00 0.00 0.00 0.00 0.00 0.70 0.08 0.22
#&gt; TCGA.S7.A7WL.01     3  0.3995    -0.2795 0.00 0.00 0.60 0.00 0.02 0.00 0.36 0.02
#&gt; TCGA.WB.A80M.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81S.01     5  0.1804     0.7437 0.08 0.00 0.00 0.00 0.90 0.00 0.00 0.02
#&gt; TCGA.S7.A7X0.01     6  0.1341     0.7393 0.00 0.00 0.00 0.08 0.00 0.92 0.00 0.00
#&gt; TCGA.SP.A6QG.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70W.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A817.01     8  0.5159     0.4260 0.00 0.00 0.16 0.00 0.00 0.30 0.02 0.52
#&gt; TCGA.RW.A7D0.01     3  0.2719     0.2858 0.00 0.00 0.80 0.00 0.18 0.00 0.00 0.02
#&gt; TCGA.TT.A6YK.01     6  0.1341     0.7393 0.00 0.00 0.00 0.08 0.00 0.92 0.00 0.00
#&gt; TCGA.SP.A6QD.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     3  0.3299    -0.1105 0.00 0.00 0.56 0.00 0.00 0.00 0.00 0.44
#&gt; TCGA.SR.A6MQ.01     3  0.4885     0.1094 0.00 0.00 0.60 0.00 0.00 0.04 0.10 0.26
#&gt; TCGA.QR.A70N.01     6  0.1341     0.7393 0.00 0.00 0.00 0.08 0.00 0.92 0.00 0.00
#&gt; TCGA.QR.A6GT.01     2  0.0471     0.9269 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A70P.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A685.01     5  0.3291     0.4458 0.00 0.00 0.28 0.00 0.70 0.00 0.00 0.02
#&gt; TCGA.QR.A70I.01     4  0.1607     0.7951 0.00 0.04 0.00 0.92 0.00 0.00 0.04 0.00
#&gt; TCGA.QR.A70K.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QC.01     3  0.3449    -0.0437 0.00 0.00 0.66 0.00 0.32 0.00 0.00 0.02
#&gt; TCGA.S7.A7WP.01     4  0.1341     0.7622 0.00 0.08 0.00 0.92 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81T.01     5  0.2224     0.6777 0.00 0.00 0.12 0.00 0.86 0.00 0.00 0.02
#&gt; TCGA.QR.A70J.01     4  0.0000     0.8255 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7X2.01     5  0.1557     0.7450 0.06 0.00 0.00 0.00 0.92 0.00 0.00 0.02
#&gt; TCGA.W2.A7HB.01     1  0.1091     0.8979 0.94 0.00 0.00 0.00 0.06 0.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     4  0.3142     0.6368 0.00 0.00 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.QR.A70G.01     3  0.2938     0.2828 0.00 0.00 0.70 0.00 0.00 0.00 0.00 0.30
#&gt; TCGA.QR.A6H5.01     4  0.3142     0.6368 0.00 0.00 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.WB.A81V.01     3  0.2547     0.3435 0.00 0.00 0.84 0.00 0.12 0.00 0.04 0.00
#&gt; TCGA.SP.A6QI.01     5  0.4396     0.3239 0.00 0.00 0.00 0.00 0.62 0.00 0.24 0.14
#&gt; TCGA.SA.A6C2.01     4  0.2407     0.8170 0.00 0.00 0.00 0.86 0.00 0.06 0.08 0.00
#&gt; TCGA.RW.A68B.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MT.01     4  0.2547     0.8120 0.00 0.00 0.00 0.84 0.00 0.04 0.12 0.00
#&gt; TCGA.RW.A67W.01     5  0.2224     0.7246 0.12 0.00 0.00 0.00 0.86 0.00 0.00 0.02
#&gt; TCGA.RW.A68G.01     5  0.1341     0.7474 0.08 0.00 0.00 0.00 0.92 0.00 0.00 0.00
#&gt; TCGA.TT.A6YO.01     2  0.4202     0.7731 0.00 0.74 0.00 0.14 0.02 0.00 0.06 0.04
#&gt; TCGA.QT.A69Q.01     5  0.1804     0.7437 0.08 0.00 0.00 0.00 0.90 0.00 0.00 0.02
#&gt; TCGA.RM.A68T.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     5  0.4396     0.3239 0.00 0.00 0.00 0.00 0.62 0.00 0.24 0.14
#&gt; TCGA.QR.A6GS.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81E.01     4  0.0808     0.8195 0.00 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.QR.A6GU.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HA.01     5  0.2020     0.7400 0.06 0.00 0.02 0.00 0.90 0.00 0.00 0.02
#&gt; TCGA.RW.A67V.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81N.01     3  0.3503     0.2788 0.00 0.00 0.78 0.00 0.02 0.00 0.12 0.08
#&gt; TCGA.WB.A80O.01     5  0.2719     0.6107 0.00 0.00 0.18 0.00 0.80 0.00 0.00 0.02
#&gt; TCGA.QT.A5XN.01     7  0.4391     0.6399 0.00 0.00 0.42 0.00 0.08 0.00 0.50 0.00
#&gt; TCGA.QR.A70M.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WW.01     6  0.2914     0.7376 0.00 0.00 0.00 0.04 0.00 0.84 0.08 0.04
#&gt; TCGA.WB.A816.01     3  0.3142     0.1744 0.00 0.00 0.64 0.00 0.00 0.00 0.00 0.36
#&gt; TCGA.QR.A70T.01     6  0.4033     0.6802 0.00 0.00 0.00 0.00 0.00 0.68 0.12 0.20
#&gt; TCGA.RW.A68F.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A705.01     2  0.0000     0.9321 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NY.05     8  0.4125     0.3485 0.00 0.00 0.44 0.00 0.00 0.02 0.02 0.52
#&gt; TCGA.SP.A6QF.01     5  0.1804     0.7473 0.08 0.00 0.00 0.00 0.90 0.00 0.00 0.02
#&gt; TCGA.QR.A707.01     5  0.4174     0.5105 0.32 0.00 0.00 0.00 0.62 0.00 0.04 0.02
#&gt; TCGA.S7.A7WO.01     2  0.4202     0.7731 0.00 0.74 0.00 0.14 0.02 0.00 0.06 0.04
#&gt; TCGA.W2.A7H5.01     3  0.5469    -0.3276 0.00 0.00 0.54 0.00 0.06 0.00 0.24 0.16
#&gt; TCGA.QT.A5XO.01     5  0.3374     0.5541 0.30 0.00 0.00 0.00 0.68 0.00 0.00 0.02
#&gt; TCGA.QR.A6GW.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A815.01     5  0.2025     0.6940 0.00 0.00 0.10 0.00 0.88 0.00 0.00 0.02
#&gt; TCGA.QR.A6ZZ.01     4  0.1341     0.7622 0.00 0.08 0.00 0.92 0.00 0.00 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     3  0.2856     0.4289 0.00 0.00 0.78 0.00 0.02 0.00 0.00 0.20
#&gt; TCGA.QR.A6H1.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YN.01     5  0.4489     0.5490 0.26 0.00 0.00 0.00 0.64 0.00 0.04 0.06
#&gt; TCGA.P7.A5NX.01     2  0.3880     0.6597 0.00 0.68 0.00 0.24 0.00 0.00 0.08 0.00
#&gt; TCGA.WB.A81J.01     5  0.4800     0.3922 0.36 0.00 0.00 0.00 0.54 0.00 0.04 0.06
#&gt; TCGA.RW.A686.01     3  0.2856     0.4289 0.00 0.00 0.78 0.00 0.02 0.00 0.00 0.20
#&gt; TCGA.WB.A81I.01     5  0.5180     0.1182 0.00 0.00 0.30 0.00 0.54 0.00 0.04 0.12
#&gt; TCGA.QT.A5XP.01     5  0.2025     0.6940 0.00 0.00 0.10 0.00 0.88 0.00 0.00 0.02
#&gt; TCGA.RW.A8AZ.01     5  0.2807     0.6822 0.04 0.00 0.00 0.00 0.84 0.00 0.02 0.10
#&gt; TCGA.W2.A7HE.01     3  0.3729    -0.2734 0.00 0.00 0.52 0.00 0.00 0.02 0.00 0.46
#&gt; TCGA.P8.A5KC.01     6  0.1341     0.7393 0.00 0.00 0.00 0.08 0.00 0.92 0.00 0.00
#&gt; TCGA.QR.A6GX.01     6  0.4213     0.6477 0.00 0.00 0.00 0.00 0.00 0.66 0.16 0.18
#&gt; TCGA.P8.A6RX.01     2  0.1563     0.8762 0.00 0.90 0.00 0.10 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XL.01     4  0.3083     0.6587 0.00 0.00 0.00 0.66 0.00 0.34 0.00 0.00
#&gt; TCGA.WB.A81A.01     6  0.5032     0.5364 0.00 0.00 0.02 0.00 0.00 0.56 0.16 0.26
#&gt; TCGA.QR.A70E.01     6  0.4458     0.6330 0.00 0.00 0.00 0.00 0.00 0.62 0.20 0.18
#&gt; TCGA.QR.A702.01     7  0.5055     0.6408 0.00 0.00 0.28 0.00 0.24 0.00 0.48 0.00
#&gt; TCGA.S7.A7WN.01     3  0.2547     0.3435 0.00 0.00 0.84 0.00 0.12 0.00 0.04 0.00
#&gt; TCGA.QR.A6GO.01     1  0.3714     0.1236 0.54 0.00 0.00 0.00 0.44 0.00 0.00 0.02
#&gt; TCGA.SR.A6MS.01     1  0.3737    -0.0367 0.50 0.00 0.00 0.00 0.48 0.00 0.00 0.02
#&gt; TCGA.SR.A6MU.01     6  0.5089     0.4641 0.00 0.00 0.02 0.00 0.00 0.52 0.14 0.32
#&gt; TCGA.QR.A70R.01     1  0.1765     0.8378 0.88 0.00 0.00 0.00 0.12 0.00 0.00 0.00
#&gt; TCGA.QR.A6GY.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.0000     0.9320 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-7-a').parent().next().next().hide();
$('#tab-node-0-get-classes-7-a').click(function(){
  $('#tab-node-0-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-0-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0-consensus-heatmap'>
<ul>
<li><a href='#tab-node-0-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-0-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0-membership-heatmap'>
<ul>
<li><a href='#tab-node-0-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-1-1.png" alt="plot of chunk tab-node-0-membership-heatmap-1"/></p>

</div>
<div id='tab-node-0-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-2-1.png" alt="plot of chunk tab-node-0-membership-heatmap-2"/></p>

</div>
<div id='tab-node-0-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-3-1.png" alt="plot of chunk tab-node-0-membership-heatmap-3"/></p>

</div>
<div id='tab-node-0-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-4-1.png" alt="plot of chunk tab-node-0-membership-heatmap-4"/></p>

</div>
<div id='tab-node-0-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-5-1.png" alt="plot of chunk tab-node-0-membership-heatmap-5"/></p>

</div>
<div id='tab-node-0-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-6-1.png" alt="plot of chunk tab-node-0-membership-heatmap-6"/></p>

</div>
<div id='tab-node-0-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-7-1.png" alt="plot of chunk tab-node-0-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-0-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-0-get-signatures'>
<ul>
<li><a href='#tab-node-0-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-0-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-0-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-0-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-0-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-0-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-0-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-1-1.png" alt="plot of chunk tab-node-0-get-signatures-1"/></p>

</div>
<div id='tab-node-0-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-2-1.png" alt="plot of chunk tab-node-0-get-signatures-2"/></p>

</div>
<div id='tab-node-0-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-3-1.png" alt="plot of chunk tab-node-0-get-signatures-3"/></p>

</div>
<div id='tab-node-0-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-4-1.png" alt="plot of chunk tab-node-0-get-signatures-4"/></p>

</div>
<div id='tab-node-0-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-5-1.png" alt="plot of chunk tab-node-0-get-signatures-5"/></p>

</div>
<div id='tab-node-0-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-6-1.png" alt="plot of chunk tab-node-0-get-signatures-6"/></p>

</div>
<div id='tab-node-0-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-7-1.png" alt="plot of chunk tab-node-0-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-0-signature_compare](figure_cola/node-0-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-0-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-0-dimension-reduction'>
<ul>
<li><a href='#tab-node-0-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-0-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-0-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-0-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-0-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-0-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-0-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-1-1.png" alt="plot of chunk tab-node-0-dimension-reduction-1"/></p>

</div>
<div id='tab-node-0-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-2-1.png" alt="plot of chunk tab-node-0-dimension-reduction-2"/></p>

</div>
<div id='tab-node-0-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-3-1.png" alt="plot of chunk tab-node-0-dimension-reduction-3"/></p>

</div>
<div id='tab-node-0-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-4-1.png" alt="plot of chunk tab-node-0-dimension-reduction-4"/></p>

</div>
<div id='tab-node-0-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-5-1.png" alt="plot of chunk tab-node-0-dimension-reduction-5"/></p>

</div>
<div id='tab-node-0-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-6-1.png" alt="plot of chunk tab-node-0-dimension-reduction-6"/></p>

</div>
<div id='tab-node-0-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-7-1.png" alt="plot of chunk tab-node-0-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-0-collect-classes](figure_cola/node-0-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node01


Parent node: [Node0](#Node0).
Child nodes: 
                Node011-leaf
        ,
                [Node012](#Node012)
        ,
                [Node013](#Node013)
        ,
                Node021-leaf
        ,
                [Node022](#Node022)
        ,
                Node023-leaf
        ,
                Node024-leaf
        ,
                [Node031](#Node031)
        ,
                [Node032](#Node032)
        ,
                Node033-leaf
        ,
                [Node041](#Node041)
        ,
                Node042-leaf
        ,
                Node043-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["01"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 64 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-01-collect-plots](figure_cola/node-01-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-01-select-partition-number](figure_cola/node-01-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           0.979       0.993         0.4871 0.516   0.516
#> 3 3 1.000           1.000       1.000         0.3540 0.753   0.553
#> 4 4 0.833           0.871       0.895         0.1123 0.871   0.646
#> 5 5 0.770           0.856       0.896         0.0633 0.961   0.852
#> 6 6 0.784           0.801       0.863         0.0307 1.000   1.000
#> 7 7 0.821           0.702       0.815         0.0318 0.948   0.772
#> 8 8 0.816           0.710       0.817         0.0206 0.959   0.780
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-01-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-01-get-classes'>
<ul>
<li><a href='#tab-node-01-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-01-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-01-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-01-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-01-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-01-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-01-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-01-get-classes-1'>
<p><a id='tab-node-01-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.WB.A80N.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.RW.A689.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.WB.A81M.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.RW.A688.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.W2.A7HF.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.S7.A7WT.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.S7.A7WX.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A80V.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.W2.A7HD.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A70V.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.WB.A81W.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.QT.A5XK.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.SR.A6MY.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.P7.A5NY.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.WB.A80Y.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.S7.A7WM.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.PR.A5PF.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.W2.A7HC.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A81D.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.RW.A681.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.RT.A6YA.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.S7.A7WR.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.SQ.A6I6.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.WB.A81R.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A818.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.SP.A6QJ.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.P8.A5KD.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A6H2.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.QR.A6H4.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.QR.A70H.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.PR.A5PG.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.RT.A6YC.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A80M.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.WB.A81S.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A70W.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A70K.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A81T.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.S7.A7X2.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.W2.A7HB.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.SP.A6QI.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.RW.A68B.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.RW.A67W.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.RW.A68G.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QT.A69Q.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A70U.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A6GS.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.W2.A7HA.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.RW.A67V.01     2   0.995      0.148 0.46 0.54
#&gt; TCGA.QR.A70M.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.SP.A6QF.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A707.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QT.A5XO.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A6GW.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A815.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A6H1.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.TT.A6YN.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.WB.A81J.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QT.A5XP.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.RW.A8AZ.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.QR.A6GO.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.SR.A6MS.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A70R.01     2   0.000      0.988 0.00 1.00
#&gt; TCGA.QR.A6GY.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.RW.A67Y.01     1   0.000      1.000 1.00 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-1-a').parent().next().next().hide();
$('#tab-node-01-get-classes-1-a').click(function(){
  $('#tab-node-01-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-2'>
<p><a id='tab-node-01-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2 p3
#&gt; TCGA.WB.A80N.01     2       0          1  0  1  0
#&gt; TCGA.RW.A689.01     2       0          1  0  1  0
#&gt; TCGA.WB.A81M.01     2       0          1  0  1  0
#&gt; TCGA.RW.A688.01     1       0          1  1  0  0
#&gt; TCGA.W2.A7HF.01     3       0          1  0  0  1
#&gt; TCGA.S7.A7WT.01     2       0          1  0  1  0
#&gt; TCGA.S7.A7WX.01     1       0          1  1  0  0
#&gt; TCGA.WB.A80V.01     1       0          1  1  0  0
#&gt; TCGA.W2.A7HD.01     2       0          1  0  1  0
#&gt; TCGA.QR.A70V.01     2       0          1  0  1  0
#&gt; TCGA.WB.A81W.01     1       0          1  1  0  0
#&gt; TCGA.QT.A5XK.01     3       0          1  0  0  1
#&gt; TCGA.SR.A6MY.01     2       0          1  0  1  0
#&gt; TCGA.P7.A5NY.01     3       0          1  0  0  1
#&gt; TCGA.WB.A80Y.01     1       0          1  1  0  0
#&gt; TCGA.S7.A7WM.01     2       0          1  0  1  0
#&gt; TCGA.PR.A5PF.01     1       0          1  1  0  0
#&gt; TCGA.W2.A7HC.01     1       0          1  1  0  0
#&gt; TCGA.WB.A81D.01     2       0          1  0  1  0
#&gt; TCGA.RW.A681.01     1       0          1  1  0  0
#&gt; TCGA.RT.A6YA.01     2       0          1  0  1  0
#&gt; TCGA.S7.A7WR.01     2       0          1  0  1  0
#&gt; TCGA.SQ.A6I6.01     2       0          1  0  1  0
#&gt; TCGA.WB.A81R.01     1       0          1  1  0  0
#&gt; TCGA.WB.A818.01     1       0          1  1  0  0
#&gt; TCGA.SP.A6QJ.01     3       0          1  0  0  1
#&gt; TCGA.P8.A5KD.01     3       0          1  0  0  1
#&gt; TCGA.QR.A6H2.01     1       0          1  1  0  0
#&gt; TCGA.QR.A6H4.01     1       0          1  1  0  0
#&gt; TCGA.QR.A70H.01     2       0          1  0  1  0
#&gt; TCGA.PR.A5PG.01     1       0          1  1  0  0
#&gt; TCGA.RT.A6YC.01     1       0          1  1  0  0
#&gt; TCGA.WB.A80M.01     2       0          1  0  1  0
#&gt; TCGA.WB.A81S.01     2       0          1  0  1  0
#&gt; TCGA.QR.A70W.01     2       0          1  0  1  0
#&gt; TCGA.QR.A70K.01     1       0          1  1  0  0
#&gt; TCGA.WB.A81T.01     3       0          1  0  0  1
#&gt; TCGA.S7.A7X2.01     3       0          1  0  0  1
#&gt; TCGA.W2.A7HB.01     2       0          1  0  1  0
#&gt; TCGA.SP.A6QI.01     3       0          1  0  0  1
#&gt; TCGA.RW.A68B.01     2       0          1  0  1  0
#&gt; TCGA.RW.A67W.01     3       0          1  0  0  1
#&gt; TCGA.RW.A68G.01     2       0          1  0  1  0
#&gt; TCGA.QT.A69Q.01     3       0          1  0  0  1
#&gt; TCGA.QR.A70U.01     3       0          1  0  0  1
#&gt; TCGA.QR.A6GS.01     1       0          1  1  0  0
#&gt; TCGA.W2.A7HA.01     1       0          1  1  0  0
#&gt; TCGA.RW.A67V.01     2       0          1  0  1  0
#&gt; TCGA.QR.A70M.01     3       0          1  0  0  1
#&gt; TCGA.SP.A6QF.01     2       0          1  0  1  0
#&gt; TCGA.QR.A707.01     2       0          1  0  1  0
#&gt; TCGA.QT.A5XO.01     2       0          1  0  1  0
#&gt; TCGA.QR.A6GW.01     1       0          1  1  0  0
#&gt; TCGA.WB.A815.01     2       0          1  0  1  0
#&gt; TCGA.QR.A6H1.01     2       0          1  0  1  0
#&gt; TCGA.TT.A6YN.01     3       0          1  0  0  1
#&gt; TCGA.WB.A81J.01     2       0          1  0  1  0
#&gt; TCGA.QT.A5XP.01     1       0          1  1  0  0
#&gt; TCGA.RW.A8AZ.01     1       0          1  1  0  0
#&gt; TCGA.QR.A6GO.01     3       0          1  0  0  1
#&gt; TCGA.SR.A6MS.01     3       0          1  0  0  1
#&gt; TCGA.QR.A70R.01     2       0          1  0  1  0
#&gt; TCGA.QR.A6GY.01     1       0          1  1  0  0
#&gt; TCGA.RW.A67Y.01     1       0          1  1  0  0
</code></pre>

<script>
$('#tab-node-01-get-classes-2-a').parent().next().next().hide();
$('#tab-node-01-get-classes-2-a').click(function(){
  $('#tab-node-01-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-3'>
<p><a id='tab-node-01-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.WB.A80N.01     2  0.0707      0.937 0.00 0.98 0.00 0.02
#&gt; TCGA.RW.A689.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A81M.01     1  0.4624      0.519 0.66 0.34 0.00 0.00
#&gt; TCGA.RW.A688.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HF.01     3  0.1211      0.975 0.00 0.00 0.96 0.04
#&gt; TCGA.S7.A7WT.01     1  0.4624      0.519 0.66 0.34 0.00 0.00
#&gt; TCGA.S7.A7WX.01     1  0.3172      0.538 0.84 0.00 0.00 0.16
#&gt; TCGA.WB.A80V.01     1  0.3172      0.669 0.84 0.00 0.00 0.16
#&gt; TCGA.W2.A7HD.01     2  0.1211      0.937 0.00 0.96 0.00 0.04
#&gt; TCGA.QR.A70V.01     2  0.4134      0.798 0.00 0.74 0.00 0.26
#&gt; TCGA.WB.A81W.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.QT.A5XK.01     3  0.0707      0.979 0.00 0.00 0.98 0.02
#&gt; TCGA.SR.A6MY.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.P7.A5NY.01     3  0.1211      0.975 0.00 0.00 0.96 0.04
#&gt; TCGA.WB.A80Y.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.S7.A7WM.01     2  0.1211      0.937 0.00 0.96 0.00 0.04
#&gt; TCGA.PR.A5PF.01     4  0.4406      0.975 0.30 0.00 0.00 0.70
#&gt; TCGA.W2.A7HC.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81D.01     2  0.2345      0.916 0.00 0.90 0.00 0.10
#&gt; TCGA.RW.A681.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.RT.A6YA.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7WR.01     2  0.1211      0.937 0.00 0.96 0.00 0.04
#&gt; TCGA.SQ.A6I6.01     2  0.1211      0.937 0.00 0.96 0.00 0.04
#&gt; TCGA.WB.A81R.01     1  0.3172      0.538 0.84 0.00 0.00 0.16
#&gt; TCGA.WB.A818.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QJ.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.P8.A5KD.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A6H2.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6H4.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.QR.A70H.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.PR.A5PG.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
#&gt; TCGA.RT.A6YC.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.WB.A80M.01     2  0.6049      0.684 0.12 0.68 0.00 0.20
#&gt; TCGA.WB.A81S.01     2  0.0707      0.937 0.00 0.98 0.00 0.02
#&gt; TCGA.QR.A70W.01     2  0.2921      0.876 0.00 0.86 0.00 0.14
#&gt; TCGA.QR.A70K.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.WB.A81T.01     3  0.0707      0.979 0.00 0.00 0.98 0.02
#&gt; TCGA.S7.A7X2.01     3  0.0707      0.979 0.00 0.00 0.98 0.02
#&gt; TCGA.W2.A7HB.01     2  0.1211      0.937 0.00 0.96 0.00 0.04
#&gt; TCGA.SP.A6QI.01     3  0.1211      0.975 0.00 0.00 0.96 0.04
#&gt; TCGA.RW.A68B.01     2  0.4134      0.798 0.00 0.74 0.00 0.26
#&gt; TCGA.RW.A67W.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A68G.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.QT.A69Q.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70U.01     3  0.1211      0.975 0.00 0.00 0.96 0.04
#&gt; TCGA.QR.A6GS.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.W2.A7HA.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67V.01     1  0.7581      0.160 0.44 0.36 0.00 0.20
#&gt; TCGA.QR.A70M.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.SP.A6QF.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A707.01     2  0.2345      0.916 0.00 0.90 0.00 0.10
#&gt; TCGA.QT.A5XO.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A6GW.01     1  0.2647      0.609 0.88 0.00 0.00 0.12
#&gt; TCGA.WB.A815.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A6H1.01     1  0.6122      0.578 0.68 0.16 0.00 0.16
#&gt; TCGA.TT.A6YN.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A81J.01     2  0.1637      0.920 0.00 0.94 0.00 0.06
#&gt; TCGA.QT.A5XP.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A8AZ.01     4  0.4406      0.975 0.30 0.00 0.00 0.70
#&gt; TCGA.QR.A6GO.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.SR.A6MS.01     3  0.0000      0.987 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70R.01     2  0.0000      0.941 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A6GY.01     4  0.4522      0.994 0.32 0.00 0.00 0.68
#&gt; TCGA.RW.A67Y.01     1  0.0000      0.756 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-3-a').parent().next().next().hide();
$('#tab-node-01-get-classes-3-a').click(function(){
  $('#tab-node-01-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-4'>
<p><a id='tab-node-01-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.WB.A80N.01     2  0.2020      0.829 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.RW.A689.01     2  0.0000      0.821 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81M.01     1  0.5958      0.447 0.64 0.24 0.00 0.04 0.08
#&gt; TCGA.RW.A688.01     1  0.0609      0.876 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.W2.A7HF.01     3  0.2331      0.919 0.00 0.00 0.90 0.08 0.02
#&gt; TCGA.S7.A7WT.01     1  0.5347      0.577 0.72 0.16 0.00 0.04 0.08
#&gt; TCGA.S7.A7WX.01     1  0.2280      0.800 0.88 0.00 0.00 0.12 0.00
#&gt; TCGA.WB.A80V.01     1  0.1410      0.844 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.W2.A7HD.01     2  0.2929      0.810 0.00 0.82 0.00 0.00 0.18
#&gt; TCGA.QR.A70V.01     5  0.2732      0.734 0.00 0.16 0.00 0.00 0.84
#&gt; TCGA.WB.A81W.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.QT.A5XK.01     3  0.0609      0.949 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.SR.A6MY.01     2  0.2516      0.822 0.00 0.86 0.00 0.00 0.14
#&gt; TCGA.P7.A5NY.01     3  0.2331      0.919 0.00 0.00 0.90 0.08 0.02
#&gt; TCGA.WB.A80Y.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.S7.A7WM.01     2  0.3274      0.789 0.00 0.78 0.00 0.00 0.22
#&gt; TCGA.PR.A5PF.01     4  0.3641      0.953 0.12 0.00 0.00 0.82 0.06
#&gt; TCGA.W2.A7HC.01     1  0.0000      0.887 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81D.01     2  0.3561      0.759 0.00 0.74 0.00 0.00 0.26
#&gt; TCGA.RW.A681.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.RT.A6YA.01     2  0.1648      0.797 0.00 0.94 0.00 0.02 0.04
#&gt; TCGA.S7.A7WR.01     2  0.3424      0.773 0.00 0.76 0.00 0.00 0.24
#&gt; TCGA.SQ.A6I6.01     2  0.3274      0.789 0.00 0.78 0.00 0.00 0.22
#&gt; TCGA.WB.A81R.01     1  0.2280      0.800 0.88 0.00 0.00 0.12 0.00
#&gt; TCGA.WB.A818.01     1  0.0000      0.887 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QJ.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A6H2.01     1  0.0000      0.887 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6H4.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.QR.A70H.01     2  0.2754      0.748 0.00 0.88 0.00 0.04 0.08
#&gt; TCGA.PR.A5PG.01     1  0.0000      0.887 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RT.A6YC.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.WB.A80M.01     5  0.4818      0.767 0.10 0.18 0.00 0.00 0.72
#&gt; TCGA.WB.A81S.01     2  0.1043      0.816 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.QR.A70W.01     2  0.3796      0.739 0.00 0.70 0.00 0.00 0.30
#&gt; TCGA.QR.A70K.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.WB.A81T.01     3  0.0609      0.949 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.S7.A7X2.01     3  0.2873      0.806 0.00 0.12 0.86 0.00 0.02
#&gt; TCGA.W2.A7HB.01     2  0.2929      0.810 0.00 0.82 0.00 0.00 0.18
#&gt; TCGA.SP.A6QI.01     3  0.2331      0.919 0.00 0.00 0.90 0.08 0.02
#&gt; TCGA.RW.A68B.01     5  0.2020      0.783 0.00 0.10 0.00 0.00 0.90
#&gt; TCGA.RW.A67W.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.RW.A68G.01     2  0.2754      0.748 0.00 0.88 0.00 0.04 0.08
#&gt; TCGA.QT.A69Q.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     3  0.2331      0.919 0.00 0.00 0.90 0.08 0.02
#&gt; TCGA.QR.A6GS.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.W2.A7HA.01     1  0.0000      0.887 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67V.01     5  0.4818      0.733 0.18 0.10 0.00 0.00 0.72
#&gt; TCGA.QR.A70M.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SP.A6QF.01     2  0.1732      0.830 0.00 0.92 0.00 0.00 0.08
#&gt; TCGA.QR.A707.01     2  0.3684      0.739 0.00 0.72 0.00 0.00 0.28
#&gt; TCGA.QT.A5XO.01     2  0.0000      0.821 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GW.01     1  0.1732      0.835 0.92 0.00 0.00 0.08 0.00
#&gt; TCGA.WB.A815.01     2  0.1043      0.808 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.QR.A6H1.01     1  0.4106      0.711 0.80 0.04 0.00 0.02 0.14
#&gt; TCGA.TT.A6YN.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A81J.01     2  0.1043      0.811 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.QT.A5XP.01     1  0.0000      0.887 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A8AZ.01     4  0.3641      0.953 0.12 0.00 0.00 0.82 0.06
#&gt; TCGA.QR.A6GO.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     3  0.0000      0.959 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70R.01     2  0.2754      0.748 0.00 0.88 0.00 0.04 0.08
#&gt; TCGA.QR.A6GY.01     4  0.2280      0.989 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.RW.A67Y.01     1  0.0000      0.887 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-4-a').parent().next().next().hide();
$('#tab-node-01-get-classes-4-a').click(function(){
  $('#tab-node-01-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-5'>
<p><a id='tab-node-01-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.WB.A80N.01     6  0.1480      0.821 0.00 0.00 0.04 0.00 0.02 0.94
#&gt; TCGA.RW.A689.01     6  0.0937      0.824 0.00 0.04 0.00 0.00 0.00 0.96
#&gt; TCGA.WB.A81M.01     1  0.6504      0.316 0.54 0.20 0.00 0.00 0.18 0.08
#&gt; TCGA.RW.A688.01     1  0.1480      0.845 0.94 0.00 0.00 0.04 0.02 0.00
#&gt; TCGA.W2.A7HF.01     3  0.3797      0.621 0.00 0.42 0.58 0.00 0.00 0.00
#&gt; TCGA.S7.A7WT.01     1  0.4541      0.650 0.74 0.04 0.00 0.00 0.16 0.06
#&gt; TCGA.S7.A7WX.01     1  0.3976      0.730 0.74 0.02 0.00 0.22 0.02 0.00
#&gt; TCGA.WB.A80V.01     1  0.1814      0.812 0.90 0.00 0.00 0.00 0.10 0.00
#&gt; TCGA.W2.A7HD.01     6  0.2512      0.814 0.00 0.06 0.00 0.00 0.06 0.88
#&gt; TCGA.QR.A70V.01     5  0.4377      0.756 0.00 0.16 0.00 0.00 0.72 0.12
#&gt; TCGA.WB.A81W.01     4  0.0547      0.952 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.QT.A5XK.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MY.01     6  0.1807      0.825 0.00 0.06 0.00 0.00 0.02 0.92
#&gt; TCGA.P7.A5NY.01     3  0.3828      0.605 0.00 0.44 0.56 0.00 0.00 0.00
#&gt; TCGA.WB.A80Y.01     4  0.0547      0.952 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.S7.A7WM.01     6  0.3544      0.769 0.00 0.12 0.00 0.00 0.08 0.80
#&gt; TCGA.PR.A5PF.01     4  0.2728      0.878 0.00 0.10 0.00 0.86 0.04 0.00
#&gt; TCGA.W2.A7HC.01     1  0.1267      0.840 0.94 0.00 0.00 0.06 0.00 0.00
#&gt; TCGA.WB.A81D.01     6  0.3567      0.759 0.00 0.10 0.00 0.00 0.10 0.80
#&gt; TCGA.RW.A681.01     4  0.0937      0.951 0.00 0.04 0.00 0.96 0.00 0.00
#&gt; TCGA.RT.A6YA.01     6  0.3351      0.769 0.04 0.16 0.00 0.00 0.00 0.80
#&gt; TCGA.S7.A7WR.01     6  0.3544      0.769 0.00 0.12 0.00 0.00 0.08 0.80
#&gt; TCGA.SQ.A6I6.01     6  0.2794      0.805 0.00 0.08 0.00 0.00 0.06 0.86
#&gt; TCGA.WB.A81R.01     1  0.2793      0.743 0.80 0.00 0.00 0.20 0.00 0.00
#&gt; TCGA.WB.A818.01     1  0.2403      0.842 0.90 0.02 0.00 0.04 0.04 0.00
#&gt; TCGA.SP.A6QJ.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     3  0.0547      0.858 0.00 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.QR.A6H2.01     1  0.2403      0.842 0.90 0.02 0.00 0.04 0.04 0.00
#&gt; TCGA.QR.A6H4.01     4  0.0937      0.951 0.00 0.04 0.00 0.96 0.00 0.00
#&gt; TCGA.QR.A70H.01     6  0.3873      0.740 0.04 0.16 0.02 0.00 0.00 0.78
#&gt; TCGA.PR.A5PG.01     1  0.1480      0.845 0.94 0.00 0.00 0.04 0.02 0.00
#&gt; TCGA.RT.A6YC.01     4  0.0547      0.952 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.WB.A80M.01     5  0.3746      0.750 0.14 0.00 0.00 0.00 0.78 0.08
#&gt; TCGA.WB.A81S.01     6  0.2790      0.780 0.00 0.14 0.02 0.00 0.00 0.84
#&gt; TCGA.QR.A70W.01     6  0.3829      0.719 0.00 0.06 0.00 0.00 0.18 0.76
#&gt; TCGA.QR.A70K.01     4  0.0937      0.951 0.00 0.04 0.00 0.96 0.00 0.00
#&gt; TCGA.WB.A81T.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7X2.01     3  0.2048      0.738 0.00 0.00 0.88 0.00 0.00 0.12
#&gt; TCGA.W2.A7HB.01     6  0.2512      0.813 0.00 0.06 0.00 0.00 0.06 0.88
#&gt; TCGA.SP.A6QI.01     3  0.3828      0.605 0.00 0.44 0.56 0.00 0.00 0.00
#&gt; TCGA.RW.A68B.01     5  0.4200      0.763 0.00 0.14 0.00 0.00 0.74 0.12
#&gt; TCGA.RW.A67W.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68G.01     6  0.4042      0.738 0.04 0.18 0.00 0.00 0.02 0.76
#&gt; TCGA.QT.A69Q.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     3  0.3828      0.605 0.00 0.44 0.56 0.00 0.00 0.00
#&gt; TCGA.QR.A6GS.01     4  0.0547      0.952 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.W2.A7HA.01     1  0.1480      0.845 0.94 0.00 0.00 0.04 0.02 0.00
#&gt; TCGA.RW.A67V.01     5  0.3660      0.725 0.16 0.00 0.00 0.00 0.78 0.06
#&gt; TCGA.QR.A70M.01     3  0.0547      0.858 0.00 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.SP.A6QF.01     6  0.1092      0.828 0.00 0.02 0.00 0.00 0.02 0.96
#&gt; TCGA.QR.A707.01     6  0.3567      0.759 0.00 0.10 0.00 0.00 0.10 0.80
#&gt; TCGA.QT.A5XO.01     6  0.0937      0.824 0.00 0.04 0.00 0.00 0.00 0.96
#&gt; TCGA.QR.A6GW.01     1  0.2631      0.763 0.82 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.WB.A815.01     6  0.3873      0.740 0.04 0.16 0.02 0.00 0.00 0.78
#&gt; TCGA.QR.A6H1.01     1  0.3523      0.705 0.78 0.04 0.00 0.00 0.18 0.00
#&gt; TCGA.TT.A6YN.01     3  0.0547      0.858 0.00 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.WB.A81J.01     6  0.1807      0.819 0.00 0.06 0.00 0.00 0.02 0.92
#&gt; TCGA.QT.A5XP.01     1  0.2403      0.842 0.90 0.02 0.00 0.04 0.04 0.00
#&gt; TCGA.RW.A8AZ.01     4  0.2350      0.910 0.00 0.10 0.00 0.88 0.02 0.00
#&gt; TCGA.QR.A6GO.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     3  0.0937      0.841 0.00 0.04 0.96 0.00 0.00 0.00
#&gt; TCGA.QR.A70R.01     6  0.3873      0.740 0.04 0.16 0.02 0.00 0.00 0.78
#&gt; TCGA.QR.A6GY.01     4  0.0937      0.951 0.00 0.04 0.00 0.96 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.2725      0.830 0.88 0.02 0.00 0.04 0.06 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-5-a').parent().next().next().hide();
$('#tab-node-01-get-classes-5-a').click(function(){
  $('#tab-node-01-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-6'>
<p><a id='tab-node-01-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.WB.A80N.01     6  0.3186     0.6492 0.00 0.22 0.02 0.00 0.00 0.76 0.00
#&gt; TCGA.RW.A689.01     6  0.3294     0.2683 0.00 0.34 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.WB.A81M.01     2  0.7295    -0.0883 0.18 0.42 0.00 0.00 0.08 0.08 0.24
#&gt; TCGA.RW.A688.01     1  0.1166     0.8105 0.94 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HF.01     3  0.3413     0.6395 0.00 0.00 0.62 0.00 0.00 0.00 0.38
#&gt; TCGA.S7.A7WT.01     1  0.7295     0.3306 0.42 0.18 0.00 0.00 0.08 0.08 0.24
#&gt; TCGA.S7.A7WX.01     1  0.3744     0.7563 0.78 0.02 0.00 0.08 0.00 0.00 0.12
#&gt; TCGA.WB.A80V.01     1  0.2804     0.7758 0.86 0.06 0.00 0.00 0.02 0.00 0.06
#&gt; TCGA.W2.A7HD.01     6  0.2081     0.7047 0.00 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.QR.A70V.01     5  0.3244     0.7591 0.00 0.04 0.00 0.00 0.78 0.18 0.00
#&gt; TCGA.WB.A81W.01     4  0.1664     0.9234 0.06 0.00 0.00 0.92 0.00 0.00 0.02
#&gt; TCGA.QT.A5XK.01     3  0.1433     0.8101 0.00 0.08 0.92 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MY.01     6  0.2422     0.6687 0.00 0.18 0.00 0.00 0.00 0.82 0.00
#&gt; TCGA.P7.A5NY.01     3  0.3459     0.6255 0.00 0.00 0.60 0.00 0.00 0.00 0.40
#&gt; TCGA.WB.A80Y.01     4  0.1664     0.9234 0.06 0.00 0.00 0.92 0.00 0.00 0.02
#&gt; TCGA.S7.A7WM.01     6  0.0000     0.6967 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.PR.A5PF.01     4  0.5251     0.7475 0.06 0.06 0.00 0.68 0.04 0.00 0.16
#&gt; TCGA.W2.A7HC.01     1  0.0504     0.8143 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.WB.A81D.01     6  0.1166     0.6750 0.00 0.06 0.00 0.00 0.00 0.94 0.00
#&gt; TCGA.RW.A681.01     4  0.0504     0.9236 0.02 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.RT.A6YA.01     2  0.3496     0.6118 0.00 0.58 0.00 0.00 0.00 0.42 0.00
#&gt; TCGA.S7.A7WR.01     6  0.0504     0.6866 0.00 0.02 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.SQ.A6I6.01     6  0.0504     0.7034 0.00 0.02 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.WB.A81R.01     1  0.1006     0.8061 0.96 0.00 0.00 0.02 0.00 0.00 0.02
#&gt; TCGA.WB.A818.01     1  0.3289     0.7791 0.82 0.02 0.00 0.00 0.06 0.00 0.10
#&gt; TCGA.SP.A6QJ.01     3  0.0000     0.8493 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     3  0.0504     0.8461 0.00 0.00 0.98 0.02 0.00 0.00 0.00
#&gt; TCGA.QR.A6H2.01     1  0.3630     0.7720 0.80 0.04 0.00 0.00 0.06 0.00 0.10
#&gt; TCGA.QR.A6H4.01     4  0.0504     0.9236 0.02 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.QR.A70H.01     2  0.3221     0.6683 0.00 0.68 0.00 0.00 0.00 0.32 0.00
#&gt; TCGA.PR.A5PG.01     1  0.0863     0.8148 0.96 0.04 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RT.A6YC.01     4  0.1664     0.9234 0.06 0.00 0.00 0.92 0.00 0.00 0.02
#&gt; TCGA.WB.A80M.01     5  0.4964     0.7579 0.02 0.08 0.00 0.00 0.66 0.02 0.22
#&gt; TCGA.WB.A81S.01     2  0.3496     0.4074 0.00 0.58 0.00 0.00 0.00 0.42 0.00
#&gt; TCGA.QR.A70W.01     6  0.4569     0.4392 0.00 0.08 0.00 0.00 0.04 0.70 0.18
#&gt; TCGA.QR.A70K.01     4  0.0504     0.9236 0.02 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.WB.A81T.01     3  0.1166     0.8217 0.00 0.06 0.94 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7X2.01     3  0.3526     0.6139 0.00 0.06 0.76 0.00 0.00 0.18 0.00
#&gt; TCGA.W2.A7HB.01     6  0.1671     0.7004 0.00 0.10 0.00 0.00 0.00 0.90 0.00
#&gt; TCGA.SP.A6QI.01     3  0.3459     0.6255 0.00 0.00 0.60 0.00 0.00 0.00 0.40
#&gt; TCGA.RW.A68B.01     5  0.2906     0.7591 0.00 0.02 0.00 0.00 0.80 0.18 0.00
#&gt; TCGA.RW.A67W.01     3  0.0000     0.8493 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68G.01     2  0.3294     0.6780 0.00 0.66 0.00 0.00 0.00 0.34 0.00
#&gt; TCGA.QT.A69Q.01     3  0.0000     0.8493 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     3  0.3459     0.6255 0.00 0.00 0.60 0.00 0.00 0.00 0.40
#&gt; TCGA.QR.A6GS.01     4  0.1664     0.9234 0.06 0.00 0.00 0.92 0.00 0.00 0.02
#&gt; TCGA.W2.A7HA.01     1  0.0863     0.8148 0.96 0.04 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67V.01     5  0.5052     0.7523 0.04 0.06 0.00 0.00 0.66 0.02 0.22
#&gt; TCGA.QR.A70M.01     3  0.0000     0.8493 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QF.01     6  0.2422     0.6420 0.00 0.18 0.00 0.00 0.00 0.82 0.00
#&gt; TCGA.QR.A707.01     6  0.1433     0.6668 0.00 0.08 0.00 0.00 0.00 0.92 0.00
#&gt; TCGA.QT.A5XO.01     6  0.3413     0.2101 0.00 0.38 0.00 0.00 0.00 0.62 0.00
#&gt; TCGA.QR.A6GW.01     1  0.0504     0.8143 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.WB.A815.01     2  0.3413     0.6741 0.00 0.62 0.00 0.00 0.00 0.38 0.00
#&gt; TCGA.QR.A6H1.01     1  0.5946     0.4890 0.52 0.10 0.00 0.00 0.10 0.00 0.28
#&gt; TCGA.TT.A6YN.01     3  0.0000     0.8493 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81J.01     6  0.3562    -0.2003 0.00 0.50 0.00 0.00 0.00 0.50 0.00
#&gt; TCGA.QT.A5XP.01     1  0.3630     0.7720 0.80 0.04 0.00 0.00 0.06 0.00 0.10
#&gt; TCGA.RW.A8AZ.01     4  0.4110     0.8056 0.02 0.06 0.00 0.78 0.04 0.00 0.10
#&gt; TCGA.QR.A6GO.01     3  0.0000     0.8493 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     3  0.1505     0.8305 0.00 0.02 0.94 0.00 0.02 0.00 0.02
#&gt; TCGA.QR.A70R.01     2  0.3358     0.6850 0.00 0.64 0.00 0.00 0.00 0.36 0.00
#&gt; TCGA.QR.A6GY.01     4  0.0504     0.9236 0.02 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.3396     0.7369 0.80 0.04 0.00 0.00 0.02 0.00 0.14
</code></pre>

<script>
$('#tab-node-01-get-classes-6-a').parent().next().next().hide();
$('#tab-node-01-get-classes-6-a').click(function(){
  $('#tab-node-01-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-7'>
<p><a id='tab-node-01-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.WB.A80N.01     6  0.3570     0.3542 0.00 0.36 0.02 0.00 0.00 0.62 0.00 0.00
#&gt; TCGA.RW.A689.01     6  0.3333    -0.2873 0.00 0.50 0.00 0.00 0.00 0.50 0.00 0.00
#&gt; TCGA.WB.A81M.01     2  0.6645     0.0914 0.14 0.48 0.00 0.00 0.20 0.08 0.10 0.00
#&gt; TCGA.RW.A688.01     1  0.2591     0.7963 0.86 0.02 0.00 0.00 0.00 0.00 0.08 0.04
#&gt; TCGA.W2.A7HF.01     8  0.3737     0.9404 0.00 0.00 0.48 0.00 0.00 0.00 0.02 0.50
#&gt; TCGA.S7.A7WT.01     1  0.6504     0.3499 0.50 0.18 0.00 0.00 0.16 0.08 0.08 0.00
#&gt; TCGA.S7.A7WX.01     1  0.1804     0.8271 0.90 0.00 0.00 0.02 0.00 0.00 0.08 0.00
#&gt; TCGA.WB.A80V.01     1  0.4022     0.7072 0.74 0.04 0.00 0.00 0.00 0.00 0.10 0.12
#&gt; TCGA.W2.A7HD.01     6  0.2569     0.6471 0.00 0.16 0.00 0.00 0.00 0.82 0.00 0.02
#&gt; TCGA.QR.A70V.01     5  0.5080     0.7098 0.00 0.00 0.00 0.00 0.54 0.10 0.32 0.04
#&gt; TCGA.WB.A81W.01     4  0.1091     0.9072 0.06 0.00 0.00 0.94 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XK.01     3  0.1275     0.8330 0.00 0.04 0.94 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.SR.A6MY.01     6  0.2719     0.5983 0.00 0.18 0.00 0.00 0.00 0.80 0.00 0.02
#&gt; TCGA.P7.A5NY.01     8  0.3318     0.9810 0.00 0.00 0.46 0.00 0.00 0.00 0.00 0.54
#&gt; TCGA.WB.A80Y.01     4  0.0471     0.9381 0.02 0.00 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WM.01     6  0.1741     0.6680 0.00 0.04 0.00 0.00 0.02 0.92 0.00 0.02
#&gt; TCGA.PR.A5PF.01     4  0.3637     0.7119 0.02 0.02 0.00 0.70 0.00 0.00 0.26 0.00
#&gt; TCGA.W2.A7HC.01     1  0.0000     0.8361 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81D.01     6  0.2348     0.6538 0.00 0.06 0.00 0.00 0.02 0.88 0.00 0.04
#&gt; TCGA.RW.A681.01     4  0.0000     0.9387 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RT.A6YA.01     2  0.3015     0.5798 0.00 0.68 0.00 0.00 0.00 0.32 0.00 0.00
#&gt; TCGA.S7.A7WR.01     6  0.1408     0.6779 0.00 0.02 0.00 0.00 0.02 0.94 0.00 0.02
#&gt; TCGA.SQ.A6I6.01     6  0.1804     0.6807 0.00 0.08 0.00 0.00 0.00 0.90 0.00 0.02
#&gt; TCGA.WB.A81R.01     1  0.0808     0.8329 0.96 0.00 0.00 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.WB.A818.01     1  0.1091     0.8302 0.94 0.00 0.00 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.SP.A6QJ.01     3  0.0000     0.8728 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     3  0.1741     0.8134 0.00 0.02 0.92 0.00 0.00 0.00 0.04 0.02
#&gt; TCGA.QR.A6H2.01     1  0.1341     0.8259 0.92 0.00 0.00 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.QR.A6H4.01     4  0.0000     0.9387 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70H.01     2  0.2680     0.6437 0.00 0.84 0.00 0.00 0.00 0.12 0.02 0.02
#&gt; TCGA.PR.A5PG.01     1  0.0471     0.8356 0.98 0.00 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.RT.A6YC.01     4  0.0471     0.9381 0.02 0.00 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80M.01     5  0.0941     0.7511 0.02 0.02 0.00 0.00 0.96 0.00 0.00 0.00
#&gt; TCGA.WB.A81S.01     2  0.2938     0.5479 0.00 0.70 0.00 0.00 0.00 0.30 0.00 0.00
#&gt; TCGA.QR.A70W.01     6  0.4559     0.4010 0.00 0.08 0.00 0.00 0.30 0.60 0.00 0.02
#&gt; TCGA.QR.A70K.01     4  0.0000     0.9387 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81T.01     3  0.1275     0.8330 0.00 0.04 0.94 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.S7.A7X2.01     3  0.3036     0.5566 0.00 0.04 0.78 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.W2.A7HB.01     6  0.1341     0.6810 0.00 0.08 0.00 0.00 0.00 0.92 0.00 0.00
#&gt; TCGA.SP.A6QI.01     8  0.3318     0.9810 0.00 0.00 0.46 0.00 0.00 0.00 0.00 0.54
#&gt; TCGA.RW.A68B.01     5  0.4174     0.7164 0.00 0.00 0.00 0.00 0.54 0.06 0.40 0.00
#&gt; TCGA.RW.A67W.01     3  0.0000     0.8728 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68G.01     2  0.2856     0.6277 0.00 0.78 0.00 0.00 0.02 0.20 0.00 0.00
#&gt; TCGA.QT.A69Q.01     3  0.0000     0.8728 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     8  0.3318     0.9810 0.00 0.00 0.46 0.00 0.00 0.00 0.00 0.54
#&gt; TCGA.QR.A6GS.01     4  0.0471     0.9381 0.02 0.00 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HA.01     1  0.0471     0.8356 0.98 0.00 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.RW.A67V.01     5  0.0941     0.7511 0.02 0.02 0.00 0.00 0.96 0.00 0.00 0.00
#&gt; TCGA.QR.A70M.01     3  0.0941     0.8461 0.00 0.02 0.96 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.SP.A6QF.01     6  0.2938     0.3913 0.00 0.30 0.00 0.00 0.00 0.70 0.00 0.00
#&gt; TCGA.QR.A707.01     6  0.3048     0.6320 0.00 0.08 0.00 0.00 0.02 0.84 0.02 0.04
#&gt; TCGA.QT.A5XO.01     2  0.3737     0.1674 0.00 0.50 0.00 0.00 0.00 0.48 0.00 0.02
#&gt; TCGA.QR.A6GW.01     1  0.0808     0.8329 0.96 0.00 0.00 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.WB.A815.01     2  0.2406     0.6631 0.00 0.80 0.00 0.00 0.00 0.20 0.00 0.00
#&gt; TCGA.QR.A6H1.01     1  0.5942     0.3342 0.50 0.06 0.00 0.00 0.30 0.04 0.10 0.00
#&gt; TCGA.TT.A6YN.01     3  0.0000     0.8728 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81J.01     2  0.3618     0.3811 0.00 0.60 0.00 0.00 0.00 0.38 0.00 0.02
#&gt; TCGA.QT.A5XP.01     1  0.1341     0.8259 0.92 0.00 0.00 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.RW.A8AZ.01     4  0.2404     0.8381 0.00 0.02 0.00 0.84 0.00 0.00 0.14 0.00
#&gt; TCGA.QR.A6GO.01     3  0.0000     0.8728 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     3  0.2862     0.6560 0.00 0.00 0.82 0.00 0.00 0.00 0.08 0.10
#&gt; TCGA.QR.A70R.01     2  0.2569     0.6618 0.00 0.82 0.00 0.00 0.00 0.16 0.00 0.02
#&gt; TCGA.QR.A6GY.01     4  0.0000     0.9387 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67Y.01     1  0.4862     0.5821 0.60 0.02 0.00 0.00 0.00 0.00 0.16 0.22
</code></pre>

<script>
$('#tab-node-01-get-classes-7-a').parent().next().next().hide();
$('#tab-node-01-get-classes-7-a').click(function(){
  $('#tab-node-01-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-01-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-01-consensus-heatmap'>
<ul>
<li><a href='#tab-node-01-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-01-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-01-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-01-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-01-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-01-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-01-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-01-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-01-membership-heatmap'>
<ul>
<li><a href='#tab-node-01-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-01-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-01-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-01-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-01-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-01-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-01-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-1-1.png" alt="plot of chunk tab-node-01-membership-heatmap-1"/></p>

</div>
<div id='tab-node-01-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-2-1.png" alt="plot of chunk tab-node-01-membership-heatmap-2"/></p>

</div>
<div id='tab-node-01-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-3-1.png" alt="plot of chunk tab-node-01-membership-heatmap-3"/></p>

</div>
<div id='tab-node-01-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-4-1.png" alt="plot of chunk tab-node-01-membership-heatmap-4"/></p>

</div>
<div id='tab-node-01-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-5-1.png" alt="plot of chunk tab-node-01-membership-heatmap-5"/></p>

</div>
<div id='tab-node-01-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-6-1.png" alt="plot of chunk tab-node-01-membership-heatmap-6"/></p>

</div>
<div id='tab-node-01-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-7-1.png" alt="plot of chunk tab-node-01-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-01-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-01-get-signatures'>
<ul>
<li><a href='#tab-node-01-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-01-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-01-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-01-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-01-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-01-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-01-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-1-1.png" alt="plot of chunk tab-node-01-get-signatures-1"/></p>

</div>
<div id='tab-node-01-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-2-1.png" alt="plot of chunk tab-node-01-get-signatures-2"/></p>

</div>
<div id='tab-node-01-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-3-1.png" alt="plot of chunk tab-node-01-get-signatures-3"/></p>

</div>
<div id='tab-node-01-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-4-1.png" alt="plot of chunk tab-node-01-get-signatures-4"/></p>

</div>
<div id='tab-node-01-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-5-1.png" alt="plot of chunk tab-node-01-get-signatures-5"/></p>

</div>
<div id='tab-node-01-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-6-1.png" alt="plot of chunk tab-node-01-get-signatures-6"/></p>

</div>
<div id='tab-node-01-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-7-1.png" alt="plot of chunk tab-node-01-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-01-signature_compare](figure_cola/node-01-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-01-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-01-dimension-reduction'>
<ul>
<li><a href='#tab-node-01-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-01-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-01-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-01-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-01-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-01-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-01-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-1-1.png" alt="plot of chunk tab-node-01-dimension-reduction-1"/></p>

</div>
<div id='tab-node-01-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-2-1.png" alt="plot of chunk tab-node-01-dimension-reduction-2"/></p>

</div>
<div id='tab-node-01-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-3-1.png" alt="plot of chunk tab-node-01-dimension-reduction-3"/></p>

</div>
<div id='tab-node-01-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-4-1.png" alt="plot of chunk tab-node-01-dimension-reduction-4"/></p>

</div>
<div id='tab-node-01-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-5-1.png" alt="plot of chunk tab-node-01-dimension-reduction-5"/></p>

</div>
<div id='tab-node-01-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-6-1.png" alt="plot of chunk tab-node-01-dimension-reduction-6"/></p>

</div>
<div id='tab-node-01-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-7-1.png" alt="plot of chunk tab-node-01-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-01-collect-classes](figure_cola/node-01-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node012


Parent node: [Node01](#Node01).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0311-leaf
        ,
                Node0312-leaf
        ,
                Node0313-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0411-leaf
        ,
                Node0412-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["012"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 27 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-012-collect-plots](figure_cola/node-012-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-012-select-partition-number](figure_cola/node-012-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5133 0.487   0.487
#> 3 3 0.883           0.961       0.930         0.1876 0.900   0.795
#> 4 4 0.850           0.929       0.945         0.1370 0.926   0.809
#> 5 5 0.753           0.801       0.860         0.0756 1.000   1.000
#> 6 6 0.717           0.413       0.791         0.0426 0.949   0.836
#> 7 7 0.690           0.643       0.787         0.0462 0.869   0.549
#> 8 8 0.677           0.610       0.773         0.0201 0.929   0.643
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-012-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-012-get-classes'>
<ul>
<li><a href='#tab-node-012-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-012-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-012-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-012-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-012-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-012-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-012-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-012-get-classes-1'>
<p><a id='tab-node-012-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.WB.A80N.01     1       0          1  1  0
#&gt; TCGA.RW.A689.01     1       0          1  1  0
#&gt; TCGA.WB.A81M.01     2       0          1  0  1
#&gt; TCGA.S7.A7WT.01     1       0          1  1  0
#&gt; TCGA.W2.A7HD.01     2       0          1  0  1
#&gt; TCGA.QR.A70V.01     2       0          1  0  1
#&gt; TCGA.SR.A6MY.01     2       0          1  0  1
#&gt; TCGA.S7.A7WM.01     1       0          1  1  0
#&gt; TCGA.WB.A81D.01     2       0          1  0  1
#&gt; TCGA.RT.A6YA.01     2       0          1  0  1
#&gt; TCGA.S7.A7WR.01     2       0          1  0  1
#&gt; TCGA.SQ.A6I6.01     1       0          1  1  0
#&gt; TCGA.QR.A70H.01     1       0          1  1  0
#&gt; TCGA.WB.A80M.01     1       0          1  1  0
#&gt; TCGA.WB.A81S.01     2       0          1  0  1
#&gt; TCGA.QR.A70W.01     1       0          1  1  0
#&gt; TCGA.W2.A7HB.01     1       0          1  1  0
#&gt; TCGA.RW.A68B.01     1       0          1  1  0
#&gt; TCGA.RW.A68G.01     1       0          1  1  0
#&gt; TCGA.RW.A67V.01     2       0          1  0  1
#&gt; TCGA.SP.A6QF.01     1       0          1  1  0
#&gt; TCGA.QR.A707.01     2       0          1  0  1
#&gt; TCGA.QT.A5XO.01     2       0          1  0  1
#&gt; TCGA.WB.A815.01     2       0          1  0  1
#&gt; TCGA.QR.A6H1.01     1       0          1  1  0
#&gt; TCGA.WB.A81J.01     1       0          1  1  0
#&gt; TCGA.QR.A70R.01     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-012-get-classes-1-a').parent().next().next().hide();
$('#tab-node-012-get-classes-1-a').click(function(){
  $('#tab-node-012-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-2'>
<p><a id='tab-node-012-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.WB.A80N.01     1  0.0892      0.959 0.98 0.02 0.00
#&gt; TCGA.RW.A689.01     1  0.0000      0.962 1.00 0.00 0.00
#&gt; TCGA.WB.A81M.01     2  0.5016      1.000 0.00 0.76 0.24
#&gt; TCGA.S7.A7WT.01     1  0.0000      0.962 1.00 0.00 0.00
#&gt; TCGA.W2.A7HD.01     2  0.5016      1.000 0.00 0.76 0.24
#&gt; TCGA.QR.A70V.01     3  0.0000      0.986 0.00 0.00 1.00
#&gt; TCGA.SR.A6MY.01     2  0.5016      1.000 0.00 0.76 0.24
#&gt; TCGA.S7.A7WM.01     1  0.0892      0.959 0.98 0.02 0.00
#&gt; TCGA.WB.A81D.01     3  0.0892      0.978 0.00 0.02 0.98
#&gt; TCGA.RT.A6YA.01     2  0.5016      1.000 0.00 0.76 0.24
#&gt; TCGA.S7.A7WR.01     3  0.0892      0.978 0.00 0.02 0.98
#&gt; TCGA.SQ.A6I6.01     1  0.1529      0.949 0.96 0.04 0.00
#&gt; TCGA.QR.A70H.01     1  0.0000      0.962 1.00 0.00 0.00
#&gt; TCGA.WB.A80M.01     1  0.0000      0.962 1.00 0.00 0.00
#&gt; TCGA.WB.A81S.01     2  0.5016      1.000 0.00 0.76 0.24
#&gt; TCGA.QR.A70W.01     1  0.0892      0.959 0.98 0.02 0.00
#&gt; TCGA.W2.A7HB.01     1  0.0892      0.959 0.98 0.02 0.00
#&gt; TCGA.RW.A68B.01     1  0.5858      0.772 0.74 0.24 0.02
#&gt; TCGA.RW.A68G.01     1  0.0000      0.962 1.00 0.00 0.00
#&gt; TCGA.RW.A67V.01     3  0.0000      0.986 0.00 0.00 1.00
#&gt; TCGA.SP.A6QF.01     1  0.0000      0.962 1.00 0.00 0.00
#&gt; TCGA.QR.A707.01     3  0.0000      0.986 0.00 0.00 1.00
#&gt; TCGA.QT.A5XO.01     2  0.5016      1.000 0.00 0.76 0.24
#&gt; TCGA.WB.A815.01     2  0.5016      1.000 0.00 0.76 0.24
#&gt; TCGA.QR.A6H1.01     1  0.0000      0.962 1.00 0.00 0.00
#&gt; TCGA.WB.A81J.01     1  0.5858      0.772 0.74 0.24 0.02
#&gt; TCGA.QR.A70R.01     1  0.0000      0.962 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-2-a').parent().next().next().hide();
$('#tab-node-012-get-classes-2-a').click(function(){
  $('#tab-node-012-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-3'>
<p><a id='tab-node-012-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.WB.A80N.01     1  0.1637      0.920 0.94 0.00 0.00 0.06
#&gt; TCGA.RW.A689.01     1  0.0707      0.932 0.98 0.00 0.00 0.02
#&gt; TCGA.WB.A81M.01     2  0.0000      0.947 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7WT.01     1  0.0000      0.937 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HD.01     2  0.0000      0.947 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70V.01     3  0.0707      0.944 0.00 0.02 0.98 0.00
#&gt; TCGA.SR.A6MY.01     2  0.1637      0.957 0.00 0.94 0.06 0.00
#&gt; TCGA.S7.A7WM.01     1  0.2345      0.899 0.90 0.00 0.00 0.10
#&gt; TCGA.WB.A81D.01     3  0.2921      0.855 0.00 0.14 0.86 0.00
#&gt; TCGA.RT.A6YA.01     2  0.0000      0.947 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7WR.01     3  0.1637      0.932 0.00 0.06 0.94 0.00
#&gt; TCGA.SQ.A6I6.01     1  0.3172      0.851 0.84 0.00 0.00 0.16
#&gt; TCGA.QR.A70H.01     1  0.0707      0.932 0.98 0.00 0.00 0.02
#&gt; TCGA.WB.A80M.01     1  0.1637      0.909 0.94 0.00 0.00 0.06
#&gt; TCGA.WB.A81S.01     2  0.2011      0.948 0.00 0.92 0.08 0.00
#&gt; TCGA.QR.A70W.01     1  0.3853      0.862 0.82 0.00 0.02 0.16
#&gt; TCGA.W2.A7HB.01     1  0.2647      0.885 0.88 0.00 0.00 0.12
#&gt; TCGA.RW.A68B.01     4  0.2011      0.980 0.08 0.00 0.00 0.92
#&gt; TCGA.RW.A68G.01     1  0.0000      0.937 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67V.01     3  0.1411      0.938 0.00 0.02 0.96 0.02
#&gt; TCGA.SP.A6QF.01     1  0.0000      0.937 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A707.01     3  0.0707      0.944 0.00 0.02 0.98 0.00
#&gt; TCGA.QT.A5XO.01     2  0.1637      0.957 0.00 0.94 0.06 0.00
#&gt; TCGA.WB.A815.01     2  0.2011      0.948 0.00 0.92 0.08 0.00
#&gt; TCGA.QR.A6H1.01     1  0.0707      0.932 0.98 0.00 0.00 0.02
#&gt; TCGA.WB.A81J.01     4  0.2706      0.979 0.08 0.00 0.02 0.90
#&gt; TCGA.QR.A70R.01     1  0.0000      0.937 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-3-a').parent().next().next().hide();
$('#tab-node-012-get-classes-3-a').click(function(){
  $('#tab-node-012-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-4'>
<p><a id='tab-node-012-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.WB.A80N.01     1  0.4728      0.742 0.70 0.00 0.00 0.06 0.24
#&gt; TCGA.RW.A689.01     1  0.0000      0.812 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81M.01     2  0.3424      0.780 0.00 0.76 0.00 0.00 0.24
#&gt; TCGA.S7.A7WT.01     1  0.1043      0.816 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.W2.A7HD.01     2  0.0609      0.893 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.QR.A70V.01     3  0.0609      0.839 0.00 0.02 0.98 0.00 0.00
#&gt; TCGA.SR.A6MY.01     2  0.0609      0.899 0.00 0.98 0.02 0.00 0.00
#&gt; TCGA.S7.A7WM.01     1  0.5245      0.712 0.64 0.00 0.00 0.08 0.28
#&gt; TCGA.WB.A81D.01     3  0.3424      0.741 0.00 0.24 0.76 0.00 0.00
#&gt; TCGA.RT.A6YA.01     2  0.3424      0.780 0.00 0.76 0.00 0.00 0.24
#&gt; TCGA.S7.A7WR.01     3  0.2732      0.808 0.00 0.16 0.84 0.00 0.00
#&gt; TCGA.SQ.A6I6.01     1  0.5487      0.685 0.62 0.00 0.00 0.10 0.28
#&gt; TCGA.QR.A70H.01     1  0.2516      0.763 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.WB.A80M.01     1  0.2516      0.770 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.WB.A81S.01     2  0.1648      0.899 0.00 0.94 0.02 0.00 0.04
#&gt; TCGA.QR.A70W.01     1  0.5156      0.674 0.62 0.00 0.00 0.06 0.32
#&gt; TCGA.W2.A7HB.01     1  0.5013      0.729 0.68 0.00 0.00 0.08 0.24
#&gt; TCGA.RW.A68B.01     4  0.3106      0.857 0.02 0.00 0.00 0.84 0.14
#&gt; TCGA.RW.A68G.01     1  0.1732      0.806 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.RW.A67V.01     3  0.2929      0.719 0.00 0.00 0.82 0.00 0.18
#&gt; TCGA.SP.A6QF.01     1  0.0609      0.814 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.QR.A707.01     3  0.0609      0.839 0.00 0.02 0.98 0.00 0.00
#&gt; TCGA.QT.A5XO.01     2  0.1216      0.898 0.00 0.96 0.02 0.00 0.02
#&gt; TCGA.WB.A815.01     2  0.1216      0.898 0.00 0.96 0.02 0.00 0.02
#&gt; TCGA.QR.A6H1.01     1  0.2516      0.796 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.WB.A81J.01     4  0.0000      0.856 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70R.01     1  0.1410      0.799 0.94 0.00 0.00 0.00 0.06
</code></pre>

<script>
$('#tab-node-012-get-classes-4-a').parent().next().next().hide();
$('#tab-node-012-get-classes-4-a').click(function(){
  $('#tab-node-012-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-5'>
<p><a id='tab-node-012-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.WB.A80N.01     1  0.4078     0.0532 0.64 0.00 0.00 0.02 0.34 0.00
#&gt; TCGA.RW.A689.01     1  0.0000     0.5974 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81M.01     6  0.3864     0.0000 0.00 0.48 0.00 0.00 0.00 0.52
#&gt; TCGA.S7.A7WT.01     1  0.1267     0.5954 0.94 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.W2.A7HD.01     2  0.2631     0.4331 0.00 0.82 0.00 0.00 0.00 0.18
#&gt; TCGA.QR.A70V.01     3  0.0547     0.7031 0.00 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.SR.A6MY.01     2  0.0547     0.6914 0.00 0.98 0.02 0.00 0.00 0.00
#&gt; TCGA.S7.A7WM.01     1  0.4144    -0.0111 0.62 0.00 0.00 0.02 0.36 0.00
#&gt; TCGA.WB.A81D.01     3  0.3578     0.5545 0.00 0.34 0.66 0.00 0.00 0.00
#&gt; TCGA.RT.A6YA.01     2  0.3797    -0.7301 0.00 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.S7.A7WR.01     3  0.2941     0.6733 0.00 0.22 0.78 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I6.01     1  0.4576    -0.2177 0.56 0.00 0.00 0.04 0.40 0.00
#&gt; TCGA.QR.A70H.01     1  0.2631     0.4865 0.82 0.00 0.00 0.00 0.18 0.00
#&gt; TCGA.WB.A80M.01     1  0.2581     0.5335 0.86 0.00 0.00 0.00 0.12 0.02
#&gt; TCGA.WB.A81S.01     2  0.0937     0.6936 0.00 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.QR.A70W.01     5  0.3647     0.0000 0.36 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.W2.A7HB.01     1  0.4246    -0.1634 0.58 0.00 0.00 0.02 0.40 0.00
#&gt; TCGA.RW.A68B.01     4  0.0547     0.9200 0.00 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.RW.A68G.01     1  0.1807     0.5768 0.92 0.00 0.00 0.00 0.06 0.02
#&gt; TCGA.RW.A67V.01     3  0.5285     0.2679 0.00 0.00 0.48 0.00 0.10 0.42
#&gt; TCGA.SP.A6QF.01     1  0.0547     0.5977 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A707.01     3  0.0547     0.7031 0.00 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.QT.A5XO.01     2  0.0000     0.7069 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A815.01     2  0.1092     0.6917 0.00 0.96 0.00 0.00 0.02 0.02
#&gt; TCGA.QR.A6H1.01     1  0.3592     0.3556 0.74 0.00 0.00 0.00 0.24 0.02
#&gt; TCGA.WB.A81J.01     4  0.2094     0.9200 0.00 0.00 0.00 0.90 0.08 0.02
#&gt; TCGA.QR.A70R.01     1  0.2581     0.5315 0.86 0.00 0.00 0.00 0.12 0.02
</code></pre>

<script>
$('#tab-node-012-get-classes-5-a').parent().next().next().hide();
$('#tab-node-012-get-classes-5-a').click(function(){
  $('#tab-node-012-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-6'>
<p><a id='tab-node-012-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.WB.A80N.01     5   0.397      0.503 0.44 0.02 0.00 0.00 0.54 0.00 0.00
#&gt; TCGA.RW.A689.01     1   0.238      0.704 0.86 0.00 0.00 0.00 0.12 0.02 0.00
#&gt; TCGA.WB.A81M.01     7   0.193      0.530 0.00 0.08 0.00 0.00 0.00 0.02 0.90
#&gt; TCGA.S7.A7WT.01     1   0.228      0.725 0.88 0.04 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.W2.A7HD.01     7   0.329      0.736 0.00 0.34 0.00 0.00 0.00 0.00 0.66
#&gt; TCGA.QR.A70V.01     3   0.000      0.689 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MY.01     7   0.466      0.768 0.00 0.40 0.04 0.00 0.00 0.02 0.54
#&gt; TCGA.S7.A7WM.01     5   0.361      0.753 0.30 0.00 0.00 0.00 0.68 0.02 0.00
#&gt; TCGA.WB.A81D.01     3   0.398      0.660 0.00 0.18 0.72 0.00 0.00 0.00 0.10
#&gt; TCGA.RT.A6YA.01     7   0.000      0.620 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.S7.A7WR.01     3   0.362      0.697 0.00 0.16 0.76 0.00 0.00 0.00 0.08
#&gt; TCGA.SQ.A6I6.01     5   0.305      0.760 0.28 0.00 0.00 0.00 0.72 0.00 0.00
#&gt; TCGA.QR.A70H.01     1   0.315      0.671 0.84 0.06 0.00 0.00 0.04 0.06 0.00
#&gt; TCGA.WB.A80M.01     1   0.470      0.558 0.68 0.20 0.00 0.00 0.08 0.04 0.00
#&gt; TCGA.WB.A81S.01     7   0.391      0.787 0.00 0.40 0.00 0.00 0.00 0.02 0.58
#&gt; TCGA.QR.A70W.01     5   0.315      0.418 0.04 0.06 0.00 0.00 0.84 0.06 0.00
#&gt; TCGA.W2.A7HB.01     5   0.352      0.759 0.28 0.00 0.00 0.00 0.70 0.02 0.00
#&gt; TCGA.RW.A68B.01     4   0.143      0.688 0.00 0.00 0.00 0.92 0.08 0.00 0.00
#&gt; TCGA.RW.A68G.01     1   0.257      0.699 0.84 0.02 0.00 0.00 0.14 0.00 0.00
#&gt; TCGA.RW.A67V.01     6   0.294      0.000 0.00 0.00 0.26 0.00 0.00 0.74 0.00
#&gt; TCGA.SP.A6QF.01     1   0.257      0.699 0.84 0.02 0.00 0.00 0.14 0.00 0.00
#&gt; TCGA.QR.A707.01     3   0.000      0.689 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XO.01     7   0.397      0.774 0.00 0.44 0.02 0.00 0.00 0.00 0.54
#&gt; TCGA.WB.A815.01     7   0.341      0.786 0.00 0.38 0.00 0.00 0.00 0.00 0.62
#&gt; TCGA.QR.A6H1.01     1   0.474      0.282 0.56 0.10 0.00 0.00 0.34 0.00 0.00
#&gt; TCGA.WB.A81J.01     4   0.426      0.687 0.00 0.14 0.00 0.74 0.04 0.08 0.00
#&gt; TCGA.QR.A70R.01     1   0.101      0.727 0.96 0.00 0.00 0.00 0.02 0.02 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-6-a').parent().next().next().hide();
$('#tab-node-012-get-classes-6-a').click(function(){
  $('#tab-node-012-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-7'>
<p><a id='tab-node-012-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.WB.A80N.01     5  0.1804      0.727 0.08 0.02 0.00 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.RW.A689.01     1  0.3618      0.754 0.60 0.02 0.00 0.00 0.38 0.00 0.00 0.00
#&gt; TCGA.WB.A81M.01     8  0.2406      0.856 0.00 0.00 0.00 0.00 0.00 0.00 0.20 0.80
#&gt; TCGA.S7.A7WT.01     1  0.3714      0.727 0.54 0.00 0.00 0.00 0.44 0.00 0.00 0.02
#&gt; TCGA.W2.A7HD.01     7  0.4530      0.271 0.06 0.02 0.00 0.00 0.00 0.02 0.66 0.24
#&gt; TCGA.QR.A70V.01     3  0.0000      0.601 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MY.01     7  0.1408      0.776 0.00 0.00 0.02 0.00 0.00 0.02 0.94 0.02
#&gt; TCGA.S7.A7WM.01     5  0.0000      0.750 0.00 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81D.01     3  0.3193      0.534 0.00 0.00 0.62 0.00 0.00 0.00 0.38 0.00
#&gt; TCGA.RT.A6YA.01     8  0.2938      0.842 0.00 0.00 0.00 0.00 0.00 0.00 0.30 0.70
#&gt; TCGA.S7.A7WR.01     3  0.2852      0.625 0.00 0.00 0.72 0.00 0.00 0.00 0.28 0.00
#&gt; TCGA.SQ.A6I6.01     5  0.0808      0.719 0.00 0.04 0.00 0.00 0.96 0.00 0.00 0.00
#&gt; TCGA.QR.A70H.01     1  0.4294      0.630 0.68 0.00 0.00 0.00 0.22 0.04 0.00 0.06
#&gt; TCGA.WB.A80M.01     1  0.5045      0.533 0.62 0.14 0.00 0.00 0.18 0.06 0.00 0.00
#&gt; TCGA.WB.A81S.01     7  0.2348      0.763 0.00 0.04 0.00 0.00 0.00 0.02 0.88 0.06
#&gt; TCGA.QR.A70W.01     2  0.3862      0.000 0.04 0.60 0.00 0.00 0.36 0.00 0.00 0.00
#&gt; TCGA.W2.A7HB.01     5  0.1091      0.745 0.06 0.00 0.00 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.RW.A68B.01     4  0.0471      0.565 0.00 0.00 0.00 0.98 0.02 0.00 0.00 0.00
#&gt; TCGA.RW.A68G.01     1  0.4105      0.736 0.54 0.00 0.00 0.00 0.42 0.02 0.00 0.02
#&gt; TCGA.RW.A67V.01     6  0.7001      0.000 0.12 0.14 0.28 0.00 0.00 0.38 0.00 0.08
#&gt; TCGA.SP.A6QF.01     1  0.4004      0.675 0.50 0.04 0.00 0.00 0.46 0.00 0.00 0.00
#&gt; TCGA.QR.A707.01     3  0.0000      0.601 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XO.01     7  0.0471      0.785 0.00 0.00 0.02 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.WB.A815.01     7  0.3131      0.755 0.00 0.04 0.04 0.00 0.00 0.02 0.84 0.06
#&gt; TCGA.QR.A6H1.01     5  0.5668      0.174 0.14 0.28 0.00 0.00 0.52 0.02 0.00 0.04
#&gt; TCGA.WB.A81J.01     4  0.3318      0.565 0.00 0.00 0.00 0.54 0.00 0.46 0.00 0.00
#&gt; TCGA.QR.A70R.01     1  0.3514      0.763 0.64 0.00 0.00 0.00 0.34 0.00 0.00 0.02
</code></pre>

<script>
$('#tab-node-012-get-classes-7-a').parent().next().next().hide();
$('#tab-node-012-get-classes-7-a').click(function(){
  $('#tab-node-012-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-012-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-012-consensus-heatmap'>
<ul>
<li><a href='#tab-node-012-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-012-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-012-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-012-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-012-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-012-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-012-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-012-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-012-membership-heatmap'>
<ul>
<li><a href='#tab-node-012-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-012-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-012-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-012-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-012-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-012-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-012-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-1-1.png" alt="plot of chunk tab-node-012-membership-heatmap-1"/></p>

</div>
<div id='tab-node-012-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-2-1.png" alt="plot of chunk tab-node-012-membership-heatmap-2"/></p>

</div>
<div id='tab-node-012-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-3-1.png" alt="plot of chunk tab-node-012-membership-heatmap-3"/></p>

</div>
<div id='tab-node-012-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-4-1.png" alt="plot of chunk tab-node-012-membership-heatmap-4"/></p>

</div>
<div id='tab-node-012-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-5-1.png" alt="plot of chunk tab-node-012-membership-heatmap-5"/></p>

</div>
<div id='tab-node-012-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-6-1.png" alt="plot of chunk tab-node-012-membership-heatmap-6"/></p>

</div>
<div id='tab-node-012-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-7-1.png" alt="plot of chunk tab-node-012-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-012-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-012-get-signatures'>
<ul>
<li><a href='#tab-node-012-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-012-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-012-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-012-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-012-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-012-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-012-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-1-1.png" alt="plot of chunk tab-node-012-get-signatures-1"/></p>

</div>
<div id='tab-node-012-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-2-1.png" alt="plot of chunk tab-node-012-get-signatures-2"/></p>

</div>
<div id='tab-node-012-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-3-1.png" alt="plot of chunk tab-node-012-get-signatures-3"/></p>

</div>
<div id='tab-node-012-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-4-1.png" alt="plot of chunk tab-node-012-get-signatures-4"/></p>

</div>
<div id='tab-node-012-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-5-1.png" alt="plot of chunk tab-node-012-get-signatures-5"/></p>

</div>
<div id='tab-node-012-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-6-1.png" alt="plot of chunk tab-node-012-get-signatures-6"/></p>

</div>
<div id='tab-node-012-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-7-1.png" alt="plot of chunk tab-node-012-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-012-signature_compare](figure_cola/node-012-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-012-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-012-dimension-reduction'>
<ul>
<li><a href='#tab-node-012-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-012-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-012-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-012-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-012-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-012-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-012-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-1-1.png" alt="plot of chunk tab-node-012-dimension-reduction-1"/></p>

</div>
<div id='tab-node-012-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-2-1.png" alt="plot of chunk tab-node-012-dimension-reduction-2"/></p>

</div>
<div id='tab-node-012-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-3-1.png" alt="plot of chunk tab-node-012-dimension-reduction-3"/></p>

</div>
<div id='tab-node-012-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-4-1.png" alt="plot of chunk tab-node-012-dimension-reduction-4"/></p>

</div>
<div id='tab-node-012-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-5-1.png" alt="plot of chunk tab-node-012-dimension-reduction-5"/></p>

</div>
<div id='tab-node-012-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-6-1.png" alt="plot of chunk tab-node-012-dimension-reduction-6"/></p>

</div>
<div id='tab-node-012-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-7-1.png" alt="plot of chunk tab-node-012-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-012-collect-classes](figure_cola/node-012-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node013


Parent node: [Node01](#Node01).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0311-leaf
        ,
                Node0312-leaf
        ,
                Node0313-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0411-leaf
        ,
                Node0412-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["013"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 15 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-013-collect-plots](figure_cola/node-013-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-013-select-partition-number](figure_cola/node-013-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5148 0.486   0.486
#> 3 3 0.895           0.970       0.973         0.3320 0.829   0.647
#> 4 4 0.781           0.771       0.904         0.0970 0.924   0.758
#> 5 5 0.714           0.618       0.863         0.0483 0.933   0.750
#> 6 6 0.705           0.537       0.867         0.0483 0.952   0.792
#> 7 7 0.790           0.559       0.875         0.0345 0.981   0.895
#> 8 8 0.819           0.477       0.875         0.0272 0.971   0.824
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-013-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-013-get-classes'>
<ul>
<li><a href='#tab-node-013-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-013-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-013-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-013-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-013-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-013-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-013-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-013-get-classes-1'>
<p><a id='tab-node-013-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.W2.A7HF.01     2       0          1  0  1
#&gt; TCGA.QT.A5XK.01     2       0          1  0  1
#&gt; TCGA.P7.A5NY.01     2       0          1  0  1
#&gt; TCGA.SP.A6QJ.01     2       0          1  0  1
#&gt; TCGA.P8.A5KD.01     2       0          1  0  1
#&gt; TCGA.WB.A81T.01     1       0          1  1  0
#&gt; TCGA.S7.A7X2.01     2       0          1  0  1
#&gt; TCGA.SP.A6QI.01     1       0          1  1  0
#&gt; TCGA.RW.A67W.01     2       0          1  0  1
#&gt; TCGA.QT.A69Q.01     1       0          1  1  0
#&gt; TCGA.QR.A70U.01     2       0          1  0  1
#&gt; TCGA.QR.A70M.01     1       0          1  1  0
#&gt; TCGA.TT.A6YN.01     1       0          1  1  0
#&gt; TCGA.QR.A6GO.01     1       0          1  1  0
#&gt; TCGA.SR.A6MS.01     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-013-get-classes-1-a').parent().next().next().hide();
$('#tab-node-013-get-classes-1-a').click(function(){
  $('#tab-node-013-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-2'>
<p><a id='tab-node-013-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.W2.A7HF.01     3   0.153      1.000 0.00 0.04 0.96
#&gt; TCGA.QT.A5XK.01     2   0.000      0.979 0.00 1.00 0.00
#&gt; TCGA.P7.A5NY.01     3   0.153      1.000 0.00 0.04 0.96
#&gt; TCGA.SP.A6QJ.01     2   0.000      0.979 0.00 1.00 0.00
#&gt; TCGA.P8.A5KD.01     2   0.000      0.979 0.00 1.00 0.00
#&gt; TCGA.WB.A81T.01     1   0.153      0.968 0.96 0.00 0.04
#&gt; TCGA.S7.A7X2.01     2   0.296      0.884 0.00 0.90 0.10
#&gt; TCGA.SP.A6QI.01     1   0.296      0.925 0.90 0.00 0.10
#&gt; TCGA.RW.A67W.01     2   0.000      0.979 0.00 1.00 0.00
#&gt; TCGA.QT.A69Q.01     1   0.000      0.971 1.00 0.00 0.00
#&gt; TCGA.QR.A70U.01     3   0.153      1.000 0.00 0.04 0.96
#&gt; TCGA.QR.A70M.01     1   0.000      0.971 1.00 0.00 0.00
#&gt; TCGA.TT.A6YN.01     1   0.153      0.968 0.96 0.00 0.04
#&gt; TCGA.QR.A6GO.01     1   0.000      0.971 1.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     2   0.000      0.979 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-2-a').parent().next().next().hide();
$('#tab-node-013-get-classes-2-a').click(function(){
  $('#tab-node-013-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-3'>
<p><a id='tab-node-013-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.W2.A7HF.01     3  0.0000      0.954 0.00 0.00 1.00 0.00
#&gt; TCGA.QT.A5XK.01     2  0.1211      0.938 0.00 0.96 0.04 0.00
#&gt; TCGA.P7.A5NY.01     3  0.2335      0.907 0.00 0.06 0.92 0.02
#&gt; TCGA.SP.A6QJ.01     2  0.0000      0.935 0.00 1.00 0.00 0.00
#&gt; TCGA.P8.A5KD.01     2  0.1211      0.938 0.00 0.96 0.04 0.00
#&gt; TCGA.WB.A81T.01     1  0.4277      0.295 0.72 0.00 0.00 0.28
#&gt; TCGA.S7.A7X2.01     2  0.3801      0.746 0.00 0.78 0.22 0.00
#&gt; TCGA.SP.A6QI.01     4  0.2921      0.546 0.14 0.00 0.00 0.86
#&gt; TCGA.RW.A67W.01     2  0.0707      0.940 0.00 0.98 0.02 0.00
#&gt; TCGA.QT.A69Q.01     1  0.1211      0.743 0.96 0.00 0.00 0.04
#&gt; TCGA.QR.A70U.01     3  0.0000      0.954 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A70M.01     1  0.2921      0.653 0.86 0.00 0.00 0.14
#&gt; TCGA.TT.A6YN.01     4  0.4948      0.332 0.44 0.00 0.00 0.56
#&gt; TCGA.QR.A6GO.01     1  0.0000      0.752 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     2  0.0000      0.935 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-3-a').parent().next().next().hide();
$('#tab-node-013-get-classes-3-a').click(function(){
  $('#tab-node-013-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-4'>
<p><a id='tab-node-013-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2  p3   p4   p5
#&gt; TCGA.W2.A7HF.01     3  0.0000      0.890 0.00 0.00 1.0 0.00 0.00
#&gt; TCGA.QT.A5XK.01     2  0.0000      0.882 0.00 1.00 0.0 0.00 0.00
#&gt; TCGA.P7.A5NY.01     3  0.3946      0.773 0.00 0.12 0.8 0.00 0.08
#&gt; TCGA.SP.A6QJ.01     2  0.0609      0.884 0.00 0.98 0.0 0.02 0.00
#&gt; TCGA.P8.A5KD.01     2  0.0609      0.884 0.00 0.98 0.0 0.02 0.00
#&gt; TCGA.WB.A81T.01     1  0.3274      0.612 0.78 0.00 0.0 0.22 0.00
#&gt; TCGA.S7.A7X2.01     2  0.3037      0.790 0.00 0.86 0.1 0.00 0.04
#&gt; TCGA.SP.A6QI.01     4  0.1732      0.000 0.08 0.00 0.0 0.92 0.00
#&gt; TCGA.RW.A67W.01     2  0.1043      0.874 0.00 0.96 0.0 0.00 0.04
#&gt; TCGA.QT.A69Q.01     1  0.0609      0.569 0.98 0.00 0.0 0.02 0.00
#&gt; TCGA.QR.A70U.01     3  0.0000      0.890 0.00 0.00 1.0 0.00 0.00
#&gt; TCGA.QR.A70M.01     5  0.4262      0.000 0.44 0.00 0.0 0.00 0.56
#&gt; TCGA.TT.A6YN.01     1  0.5173      0.101 0.50 0.00 0.0 0.46 0.04
#&gt; TCGA.QR.A6GO.01     1  0.1216      0.552 0.96 0.00 0.0 0.02 0.02
#&gt; TCGA.SR.A6MS.01     2  0.5425      0.563 0.00 0.60 0.0 0.08 0.32
</code></pre>

<script>
$('#tab-node-013-get-classes-4-a').parent().next().next().hide();
$('#tab-node-013-get-classes-4-a').click(function(){
  $('#tab-node-013-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-5'>
<p><a id='tab-node-013-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.W2.A7HF.01     3  0.0000      0.680 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XK.01     2  0.1092      0.801 0.00 0.96 0.02 0.00 0.00 0.02
#&gt; TCGA.P7.A5NY.01     3  0.5618      0.210 0.00 0.34 0.50 0.00 0.00 0.16
#&gt; TCGA.SP.A6QJ.01     2  0.1556      0.794 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.P8.A5KD.01     2  0.1814      0.772 0.00 0.90 0.00 0.00 0.00 0.10
#&gt; TCGA.WB.A81T.01     1  0.1865      0.757 0.92 0.00 0.00 0.04 0.04 0.00
#&gt; TCGA.S7.A7X2.01     2  0.4393      0.567 0.00 0.72 0.14 0.00 0.00 0.14
#&gt; TCGA.SP.A6QI.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.RW.A67W.01     2  0.1556      0.787 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.QT.A69Q.01     1  0.2956      0.720 0.84 0.00 0.00 0.00 0.12 0.04
#&gt; TCGA.QR.A70U.01     3  0.0000      0.680 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70M.01     5  0.0547      0.000 0.02 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.TT.A6YN.01     1  0.3460      0.604 0.76 0.00 0.00 0.22 0.02 0.00
#&gt; TCGA.QR.A6GO.01     1  0.2941      0.688 0.78 0.00 0.00 0.00 0.22 0.00
#&gt; TCGA.SR.A6MS.01     6  0.2793      0.000 0.00 0.20 0.00 0.00 0.00 0.80
</code></pre>

<script>
$('#tab-node-013-get-classes-5-a').parent().next().next().hide();
$('#tab-node-013-get-classes-5-a').click(function(){
  $('#tab-node-013-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-6'>
<p><a id='tab-node-013-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.W2.A7HF.01     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XK.01     2  0.1671      0.846 0.00 0.90 0.00 0.00 0.00 0.00 0.10
#&gt; TCGA.P7.A5NY.01     7  0.4547      0.000 0.00 0.08 0.34 0.00 0.00 0.00 0.58
#&gt; TCGA.SP.A6QJ.01     2  0.1363      0.856 0.00 0.94 0.00 0.00 0.00 0.02 0.04
#&gt; TCGA.P8.A5KD.01     2  0.0863      0.854 0.00 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.WB.A81T.01     1  0.2569      0.689 0.84 0.00 0.00 0.02 0.14 0.00 0.00
#&gt; TCGA.S7.A7X2.01     2  0.4015      0.577 0.00 0.68 0.06 0.00 0.00 0.00 0.26
#&gt; TCGA.SP.A6QI.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67W.01     2  0.0863      0.839 0.00 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.QT.A69Q.01     1  0.2722      0.601 0.84 0.00 0.00 0.00 0.04 0.00 0.12
#&gt; TCGA.QR.A70U.01     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70M.01     5  0.4789      0.000 0.14 0.00 0.00 0.00 0.60 0.00 0.26
#&gt; TCGA.TT.A6YN.01     1  0.5429      0.439 0.48 0.00 0.00 0.06 0.40 0.00 0.06
#&gt; TCGA.QR.A6GO.01     1  0.0000      0.689 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MS.01     6  0.0000      0.000 0.00 0.00 0.00 0.00 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-6-a').parent().next().next().hide();
$('#tab-node-013-get-classes-6-a').click(function(){
  $('#tab-node-013-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-7'>
<p><a id='tab-node-013-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.W2.A7HF.01     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XK.01     2  0.0471      0.847 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.P7.A5NY.01     7  0.3299      0.000 0.00 0.06 0.18 0.00 0.00 0.00 0.76 0.00
#&gt; TCGA.SP.A6QJ.01     2  0.1091      0.834 0.00 0.94 0.00 0.00 0.00 0.06 0.00 0.00
#&gt; TCGA.P8.A5KD.01     2  0.0941      0.843 0.00 0.96 0.00 0.00 0.00 0.00 0.02 0.02
#&gt; TCGA.WB.A81T.01     1  0.1091      0.408 0.94 0.00 0.00 0.00 0.00 0.00 0.00 0.06
#&gt; TCGA.S7.A7X2.01     2  0.3589      0.645 0.00 0.74 0.10 0.00 0.00 0.00 0.16 0.00
#&gt; TCGA.SP.A6QI.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67W.01     2  0.3178      0.761 0.00 0.80 0.00 0.00 0.00 0.02 0.14 0.04
#&gt; TCGA.QT.A69Q.01     1  0.5062      0.320 0.48 0.00 0.00 0.00 0.02 0.00 0.12 0.38
#&gt; TCGA.QR.A70U.01     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70M.01     5  0.0471      0.000 0.02 0.00 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.TT.A6YN.01     8  0.4518      0.000 0.36 0.00 0.00 0.06 0.00 0.00 0.02 0.56
#&gt; TCGA.QR.A6GO.01     1  0.1804      0.498 0.90 0.00 0.00 0.00 0.08 0.00 0.02 0.00
#&gt; TCGA.SR.A6MS.01     6  0.0000      0.000 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-7-a').parent().next().next().hide();
$('#tab-node-013-get-classes-7-a').click(function(){
  $('#tab-node-013-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-013-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-013-consensus-heatmap'>
<ul>
<li><a href='#tab-node-013-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-013-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-013-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-013-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-013-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-013-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-013-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-013-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-013-membership-heatmap'>
<ul>
<li><a href='#tab-node-013-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-013-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-013-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-013-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-013-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-013-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-013-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-1-1.png" alt="plot of chunk tab-node-013-membership-heatmap-1"/></p>

</div>
<div id='tab-node-013-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-2-1.png" alt="plot of chunk tab-node-013-membership-heatmap-2"/></p>

</div>
<div id='tab-node-013-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-3-1.png" alt="plot of chunk tab-node-013-membership-heatmap-3"/></p>

</div>
<div id='tab-node-013-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-4-1.png" alt="plot of chunk tab-node-013-membership-heatmap-4"/></p>

</div>
<div id='tab-node-013-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-5-1.png" alt="plot of chunk tab-node-013-membership-heatmap-5"/></p>

</div>
<div id='tab-node-013-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-6-1.png" alt="plot of chunk tab-node-013-membership-heatmap-6"/></p>

</div>
<div id='tab-node-013-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-7-1.png" alt="plot of chunk tab-node-013-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-013-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-013-get-signatures'>
<ul>
<li><a href='#tab-node-013-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-013-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-013-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-013-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-013-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-013-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-013-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-1-1.png" alt="plot of chunk tab-node-013-get-signatures-1"/></p>

</div>
<div id='tab-node-013-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-2-1.png" alt="plot of chunk tab-node-013-get-signatures-2"/></p>

</div>
<div id='tab-node-013-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-3-1.png" alt="plot of chunk tab-node-013-get-signatures-3"/></p>

</div>
<div id='tab-node-013-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-4-1.png" alt="plot of chunk tab-node-013-get-signatures-4"/></p>

</div>
<div id='tab-node-013-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-5-1.png" alt="plot of chunk tab-node-013-get-signatures-5"/></p>

</div>
<div id='tab-node-013-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-6-1.png" alt="plot of chunk tab-node-013-get-signatures-6"/></p>

</div>
<div id='tab-node-013-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-7-1.png" alt="plot of chunk tab-node-013-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-013-signature_compare](figure_cola/node-013-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-013-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-013-dimension-reduction'>
<ul>
<li><a href='#tab-node-013-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-013-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-013-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-013-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-013-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-013-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-013-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-1-1.png" alt="plot of chunk tab-node-013-dimension-reduction-1"/></p>

</div>
<div id='tab-node-013-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-2-1.png" alt="plot of chunk tab-node-013-dimension-reduction-2"/></p>

</div>
<div id='tab-node-013-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-3-1.png" alt="plot of chunk tab-node-013-dimension-reduction-3"/></p>

</div>
<div id='tab-node-013-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-4-1.png" alt="plot of chunk tab-node-013-dimension-reduction-4"/></p>

</div>
<div id='tab-node-013-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-5-1.png" alt="plot of chunk tab-node-013-dimension-reduction-5"/></p>

</div>
<div id='tab-node-013-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-6-1.png" alt="plot of chunk tab-node-013-dimension-reduction-6"/></p>

</div>
<div id='tab-node-013-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-7-1.png" alt="plot of chunk tab-node-013-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-013-collect-classes](figure_cola/node-013-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node02


Parent node: [Node0](#Node0).
Child nodes: 
                Node011-leaf
        ,
                [Node012](#Node012)
        ,
                [Node013](#Node013)
        ,
                Node021-leaf
        ,
                [Node022](#Node022)
        ,
                Node023-leaf
        ,
                Node024-leaf
        ,
                [Node031](#Node031)
        ,
                [Node032](#Node032)
        ,
                Node033-leaf
        ,
                [Node041](#Node041)
        ,
                Node042-leaf
        ,
                Node043-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["02"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 40 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 4.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-02-collect-plots](figure_cola/node-02-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-02-select-partition-number](figure_cola/node-02-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 0.858           0.922       0.967         0.4218 0.550   0.550
#> 3 3 1.000           0.967       0.971         0.2098 0.949   0.907
#> 4 4 1.000           0.962       0.987         0.3558 0.805   0.609
#> 5 5 0.900           0.877       0.947         0.0524 0.977   0.924
#> 6 6 0.788           0.780       0.885         0.0541 0.991   0.968
#> 7 7 0.775           0.470       0.822         0.0416 0.978   0.920
#> 8 8 0.782           0.625       0.784         0.0179 0.882   0.547
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 4
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-02-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-02-get-classes'>
<ul>
<li><a href='#tab-node-02-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-02-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-02-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-02-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-02-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-02-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-02-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-02-get-classes-1'>
<p><a id='tab-node-02-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.QR.A6H6.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A6GZ.01     1    0.00      0.886 1.00 0.00
#&gt; TCGA.QR.A7IP.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.W2.A7H7.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A6H0.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.P8.A5KC.11     1    0.00      0.886 1.00 0.00
#&gt; TCGA.SQ.A6I4.11     1    0.00      0.886 1.00 0.00
#&gt; TCGA.RM.A68W.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QT.A5XJ.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.P8.A5KD.11     1    0.00      0.886 1.00 0.00
#&gt; TCGA.QR.A70D.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.WB.A80P.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.RW.A7CZ.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.SR.A6MX.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.WB.A822.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.SR.A6MX.05     2    0.00      1.000 0.00 1.00
#&gt; TCGA.RW.A680.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A6H3.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.SR.A6MX.06     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A703.01     1    0.00      0.886 1.00 0.00
#&gt; TCGA.XG.A823.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.WB.A81G.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.WB.A814.01     1    0.00      0.886 1.00 0.00
#&gt; TCGA.QR.A70Q.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.SP.A6QG.01     1    0.99      0.345 0.56 0.44
#&gt; TCGA.SP.A6QD.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A6GT.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A70P.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A70I.01     1    0.99      0.345 0.56 0.44
#&gt; TCGA.S7.A7WP.01     1    0.00      0.886 1.00 0.00
#&gt; TCGA.TT.A6YO.01     1    0.00      0.886 1.00 0.00
#&gt; TCGA.RM.A68T.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.WB.A81E.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A6GU.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.RW.A68F.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.QR.A705.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.S7.A7WO.01     1    0.00      0.886 1.00 0.00
#&gt; TCGA.QR.A6ZZ.01     1    0.00      0.886 1.00 0.00
#&gt; TCGA.P7.A5NX.01     2    0.00      1.000 0.00 1.00
#&gt; TCGA.P8.A6RX.01     1    0.99      0.345 0.56 0.44
</code></pre>

<script>
$('#tab-node-02-get-classes-1-a').parent().next().next().hide();
$('#tab-node-02-get-classes-1-a').click(function(){
  $('#tab-node-02-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-2'>
<p><a id='tab-node-02-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.QR.A6H6.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A6GZ.01     1   0.000      0.956 1.00 0.00 0.00
#&gt; TCGA.QR.A7IP.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.W2.A7H7.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A6H0.01     2   0.254      0.941 0.00 0.92 0.08
#&gt; TCGA.P8.A5KC.11     3   0.254      1.000 0.08 0.00 0.92
#&gt; TCGA.SQ.A6I4.11     3   0.254      1.000 0.08 0.00 0.92
#&gt; TCGA.RM.A68W.01     2   0.254      0.941 0.00 0.92 0.08
#&gt; TCGA.QT.A5XJ.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.P8.A5KD.11     3   0.254      1.000 0.08 0.00 0.92
#&gt; TCGA.QR.A70D.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.WB.A80P.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.RW.A7CZ.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.SR.A6MX.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.WB.A822.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.SR.A6MX.05     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.RW.A680.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A6H3.01     2   0.254      0.941 0.00 0.92 0.08
#&gt; TCGA.SR.A6MX.06     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A703.01     1   0.000      0.956 1.00 0.00 0.00
#&gt; TCGA.XG.A823.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.WB.A81G.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.WB.A814.01     1   0.000      0.956 1.00 0.00 0.00
#&gt; TCGA.QR.A70Q.01     2   0.254      0.941 0.00 0.92 0.08
#&gt; TCGA.SP.A6QG.01     1   0.207      0.928 0.94 0.06 0.00
#&gt; TCGA.SP.A6QD.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A6GT.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A70P.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A70I.01     1   0.207      0.928 0.94 0.06 0.00
#&gt; TCGA.S7.A7WP.01     1   0.000      0.956 1.00 0.00 0.00
#&gt; TCGA.TT.A6YO.01     3   0.254      1.000 0.08 0.00 0.92
#&gt; TCGA.RM.A68T.01     2   0.254      0.941 0.00 0.92 0.08
#&gt; TCGA.WB.A81E.01     2   0.254      0.941 0.00 0.92 0.08
#&gt; TCGA.QR.A6GU.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.RW.A68F.01     2   0.000      0.978 0.00 1.00 0.00
#&gt; TCGA.QR.A705.01     2   0.254      0.941 0.00 0.92 0.08
#&gt; TCGA.S7.A7WO.01     3   0.254      1.000 0.08 0.00 0.92
#&gt; TCGA.QR.A6ZZ.01     1   0.000      0.956 1.00 0.00 0.00
#&gt; TCGA.P7.A5NX.01     2   0.153      0.961 0.00 0.96 0.04
#&gt; TCGA.P8.A6RX.01     1   0.207      0.928 0.94 0.06 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-2-a').parent().next().next().hide();
$('#tab-node-02-get-classes-2-a').click(function(){
  $('#tab-node-02-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-3'>
<p><a id='tab-node-02-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4
#&gt; TCGA.QR.A6H6.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A6GZ.01     1   0.000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.QR.A7IP.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.W2.A7H7.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A6H0.01     4   0.000      0.916 0.00 0.00  0 1.00
#&gt; TCGA.P8.A5KC.11     3   0.000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.SQ.A6I4.11     3   0.000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.RM.A68W.01     4   0.000      0.916 0.00 0.00  0 1.00
#&gt; TCGA.QT.A5XJ.01     2   0.320      0.868 0.08 0.88  0 0.04
#&gt; TCGA.P8.A5KD.11     3   0.000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.QR.A70D.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.WB.A80P.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.RW.A7CZ.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.SR.A6MX.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.WB.A822.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.SR.A6MX.05     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.RW.A680.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A6H3.01     4   0.000      0.916 0.00 0.00  0 1.00
#&gt; TCGA.SR.A6MX.06     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A703.01     1   0.000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.XG.A823.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.WB.A81G.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.WB.A814.01     1   0.000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.QR.A70Q.01     4   0.000      0.916 0.00 0.00  0 1.00
#&gt; TCGA.SP.A6QG.01     1   0.000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.SP.A6QD.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A6GT.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A70P.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A70I.01     1   0.000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.S7.A7WP.01     1   0.000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.TT.A6YO.01     3   0.000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.RM.A68T.01     4   0.000      0.916 0.00 0.00  0 1.00
#&gt; TCGA.WB.A81E.01     4   0.000      0.916 0.00 0.00  0 1.00
#&gt; TCGA.QR.A6GU.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.RW.A68F.01     2   0.000      0.993 0.00 1.00  0 0.00
#&gt; TCGA.QR.A705.01     4   0.000      0.916 0.00 0.00  0 1.00
#&gt; TCGA.S7.A7WO.01     3   0.000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.QR.A6ZZ.01     1   0.000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.P7.A5NX.01     4   0.485      0.328 0.00 0.40  0 0.60
#&gt; TCGA.P8.A6RX.01     1   0.000      1.000 1.00 0.00  0 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-3-a').parent().next().next().hide();
$('#tab-node-02-get-classes-3-a').click(function(){
  $('#tab-node-02-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-4'>
<p><a id='tab-node-02-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5
#&gt; TCGA.QR.A6H6.01     2  0.1410      0.937 0.00 0.94  0 0.00 0.06
#&gt; TCGA.QR.A6GZ.01     1  0.0000      0.960 1.00 0.00  0 0.00 0.00
#&gt; TCGA.QR.A7IP.01     2  0.2280      0.883 0.00 0.88  0 0.00 0.12
#&gt; TCGA.W2.A7H7.01     2  0.1410      0.937 0.00 0.94  0 0.00 0.06
#&gt; TCGA.QR.A6H0.01     4  0.0000      0.873 0.00 0.00  0 1.00 0.00
#&gt; TCGA.P8.A5KC.11     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.SQ.A6I4.11     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.RM.A68W.01     4  0.0000      0.873 0.00 0.00  0 1.00 0.00
#&gt; TCGA.QT.A5XJ.01     5  0.2516      0.000 0.00 0.14  0 0.00 0.86
#&gt; TCGA.P8.A5KD.11     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.QR.A70D.01     2  0.1043      0.939 0.00 0.96  0 0.00 0.04
#&gt; TCGA.WB.A80P.01     2  0.1043      0.932 0.00 0.96  0 0.00 0.04
#&gt; TCGA.RW.A7CZ.01     2  0.0609      0.937 0.00 0.98  0 0.00 0.02
#&gt; TCGA.SR.A6MX.01     2  0.1043      0.932 0.00 0.96  0 0.00 0.04
#&gt; TCGA.WB.A822.01     2  0.1410      0.937 0.00 0.94  0 0.00 0.06
#&gt; TCGA.SR.A6MX.05     2  0.1043      0.932 0.00 0.96  0 0.00 0.04
#&gt; TCGA.RW.A680.01     2  0.1043      0.932 0.00 0.96  0 0.00 0.04
#&gt; TCGA.QR.A6H3.01     4  0.0000      0.873 0.00 0.00  0 1.00 0.00
#&gt; TCGA.SR.A6MX.06     2  0.1043      0.932 0.00 0.96  0 0.00 0.04
#&gt; TCGA.QR.A703.01     1  0.0000      0.960 1.00 0.00  0 0.00 0.00
#&gt; TCGA.XG.A823.01     2  0.1410      0.937 0.00 0.94  0 0.00 0.06
#&gt; TCGA.WB.A81G.01     2  0.0000      0.940 0.00 1.00  0 0.00 0.00
#&gt; TCGA.WB.A814.01     1  0.0000      0.960 1.00 0.00  0 0.00 0.00
#&gt; TCGA.QR.A70Q.01     4  0.0000      0.873 0.00 0.00  0 1.00 0.00
#&gt; TCGA.SP.A6QG.01     1  0.2280      0.902 0.88 0.00  0 0.00 0.12
#&gt; TCGA.SP.A6QD.01     2  0.1410      0.937 0.00 0.94  0 0.00 0.06
#&gt; TCGA.QR.A6GT.01     2  0.1043      0.932 0.00 0.96  0 0.00 0.04
#&gt; TCGA.QR.A70P.01     2  0.1410      0.937 0.00 0.94  0 0.00 0.06
#&gt; TCGA.QR.A70I.01     1  0.2280      0.902 0.88 0.00  0 0.00 0.12
#&gt; TCGA.S7.A7WP.01     1  0.0000      0.960 1.00 0.00  0 0.00 0.00
#&gt; TCGA.TT.A6YO.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.RM.A68T.01     4  0.0000      0.873 0.00 0.00  0 1.00 0.00
#&gt; TCGA.WB.A81E.01     4  0.1410      0.842 0.00 0.00  0 0.94 0.06
#&gt; TCGA.QR.A6GU.01     2  0.1410      0.937 0.00 0.94  0 0.00 0.06
#&gt; TCGA.RW.A68F.01     2  0.1043      0.928 0.00 0.96  0 0.00 0.04
#&gt; TCGA.QR.A705.01     4  0.1043      0.855 0.00 0.00  0 0.96 0.04
#&gt; TCGA.S7.A7WO.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.QR.A6ZZ.01     1  0.0000      0.960 1.00 0.00  0 0.00 0.00
#&gt; TCGA.P7.A5NX.01     4  0.6824     -0.294 0.00 0.32  0 0.34 0.34
#&gt; TCGA.P8.A6RX.01     1  0.1410      0.938 0.94 0.00  0 0.00 0.06
</code></pre>

<script>
$('#tab-node-02-get-classes-4-a').parent().next().next().hide();
$('#tab-node-02-get-classes-4-a').click(function(){
  $('#tab-node-02-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-5'>
<p><a id='tab-node-02-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6
#&gt; TCGA.QR.A6H6.01     2  0.3198      0.763 0.00 0.74  0 0.00 0.00 0.26
#&gt; TCGA.QR.A6GZ.01     1  0.0000      0.878 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.QR.A7IP.01     2  0.3409      0.727 0.00 0.70  0 0.00 0.00 0.30
#&gt; TCGA.W2.A7H7.01     2  0.3198      0.763 0.00 0.74  0 0.00 0.00 0.26
#&gt; TCGA.QR.A6H0.01     4  0.0000      0.965 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.P8.A5KC.11     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.11     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.RM.A68W.01     4  0.0000      0.965 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.QT.A5XJ.01     5  0.1807      0.000 0.00 0.02  0 0.00 0.92 0.06
#&gt; TCGA.P8.A5KD.11     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.QR.A70D.01     2  0.2454      0.779 0.00 0.84  0 0.00 0.00 0.16
#&gt; TCGA.WB.A80P.01     2  0.1480      0.716 0.00 0.94  0 0.00 0.02 0.04
#&gt; TCGA.RW.A7CZ.01     2  0.0000      0.749 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.01     2  0.2981      0.601 0.00 0.82  0 0.00 0.02 0.16
#&gt; TCGA.WB.A822.01     2  0.3076      0.769 0.00 0.76  0 0.00 0.00 0.24
#&gt; TCGA.SR.A6MX.05     2  0.2981      0.601 0.00 0.82  0 0.00 0.02 0.16
#&gt; TCGA.RW.A680.01     2  0.1480      0.716 0.00 0.94  0 0.00 0.02 0.04
#&gt; TCGA.QR.A6H3.01     4  0.0000      0.965 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.SR.A6MX.06     2  0.2981      0.601 0.00 0.82  0 0.00 0.02 0.16
#&gt; TCGA.QR.A703.01     1  0.0000      0.878 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.XG.A823.01     2  0.3198      0.763 0.00 0.74  0 0.00 0.00 0.26
#&gt; TCGA.WB.A81G.01     2  0.1267      0.768 0.00 0.94  0 0.00 0.00 0.06
#&gt; TCGA.WB.A814.01     1  0.1556      0.856 0.92 0.00  0 0.00 0.00 0.08
#&gt; TCGA.QR.A70Q.01     4  0.0547      0.959 0.00 0.00  0 0.98 0.00 0.02
#&gt; TCGA.SP.A6QG.01     1  0.3409      0.694 0.70 0.00  0 0.00 0.00 0.30
#&gt; TCGA.SP.A6QD.01     2  0.3198      0.763 0.00 0.74  0 0.00 0.00 0.26
#&gt; TCGA.QR.A6GT.01     2  0.0000      0.749 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.QR.A70P.01     2  0.2631      0.778 0.00 0.82  0 0.00 0.00 0.18
#&gt; TCGA.QR.A70I.01     1  0.4078      0.663 0.64 0.00  0 0.00 0.02 0.34
#&gt; TCGA.S7.A7WP.01     1  0.0000      0.878 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.TT.A6YO.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.RM.A68T.01     4  0.0000      0.965 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.WB.A81E.01     4  0.2094      0.907 0.00 0.00  0 0.90 0.02 0.08
#&gt; TCGA.QR.A6GU.01     2  0.3198      0.763 0.00 0.74  0 0.00 0.00 0.26
#&gt; TCGA.RW.A68F.01     2  0.3567      0.616 0.00 0.80  0 0.00 0.10 0.10
#&gt; TCGA.QR.A705.01     4  0.1556      0.925 0.00 0.00  0 0.92 0.00 0.08
#&gt; TCGA.S7.A7WO.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.QR.A6ZZ.01     1  0.0000      0.878 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.P7.A5NX.01     6  0.7512      0.000 0.00 0.24  0 0.16 0.24 0.36
#&gt; TCGA.P8.A6RX.01     1  0.2581      0.818 0.86 0.00  0 0.00 0.02 0.12
</code></pre>

<script>
$('#tab-node-02-get-classes-5-a').parent().next().next().hide();
$('#tab-node-02-get-classes-5-a').click(function(){
  $('#tab-node-02-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-6'>
<p><a id='tab-node-02-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6   p7
#&gt; TCGA.QR.A6H6.01     2  0.3139    -0.0844 0.00 0.70  0 0.00 0.00 0.00 0.30
#&gt; TCGA.QR.A6GZ.01     1  0.1006     0.8211 0.96 0.00  0 0.00 0.02 0.02 0.00
#&gt; TCGA.QR.A7IP.01     7  0.3994     0.0000 0.00 0.48  0 0.00 0.00 0.02 0.50
#&gt; TCGA.W2.A7H7.01     2  0.3815    -0.3229 0.00 0.62  0 0.00 0.00 0.02 0.36
#&gt; TCGA.QR.A6H0.01     4  0.1006     0.8779 0.00 0.00  0 0.96 0.00 0.02 0.02
#&gt; TCGA.P8.A5KC.11     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.11     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.RM.A68W.01     4  0.0504     0.8850 0.00 0.00  0 0.98 0.00 0.02 0.00
#&gt; TCGA.QT.A5XJ.01     5  0.0863     0.0000 0.00 0.00  0 0.00 0.96 0.00 0.04
#&gt; TCGA.P8.A5KD.11     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70D.01     2  0.2708     0.1216 0.00 0.78  0 0.00 0.00 0.00 0.22
#&gt; TCGA.WB.A80P.01     2  0.1433     0.4131 0.00 0.92  0 0.00 0.00 0.08 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.1006     0.4187 0.00 0.96  0 0.00 0.00 0.02 0.02
#&gt; TCGA.SR.A6MX.01     2  0.3745     0.3314 0.00 0.70  0 0.00 0.00 0.04 0.26
#&gt; TCGA.WB.A822.01     2  0.3047    -0.0351 0.00 0.72  0 0.00 0.00 0.00 0.28
#&gt; TCGA.SR.A6MX.05     2  0.3745     0.3314 0.00 0.70  0 0.00 0.00 0.04 0.26
#&gt; TCGA.RW.A680.01     2  0.1928     0.4173 0.00 0.90  0 0.00 0.00 0.02 0.08
#&gt; TCGA.QR.A6H3.01     4  0.1006     0.8827 0.00 0.00  0 0.96 0.00 0.02 0.02
#&gt; TCGA.SR.A6MX.06     2  0.3745     0.3314 0.00 0.70  0 0.00 0.00 0.04 0.26
#&gt; TCGA.QR.A703.01     1  0.0000     0.8249 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.XG.A823.01     2  0.3294    -0.2390 0.00 0.66  0 0.00 0.00 0.00 0.34
#&gt; TCGA.WB.A81G.01     2  0.1718     0.3719 0.00 0.92  0 0.00 0.00 0.04 0.04
#&gt; TCGA.WB.A814.01     1  0.1006     0.8189 0.96 0.00  0 0.00 0.00 0.02 0.02
#&gt; TCGA.QR.A70Q.01     4  0.2159     0.8662 0.00 0.00  0 0.90 0.02 0.06 0.02
#&gt; TCGA.SP.A6QG.01     1  0.5234     0.5036 0.56 0.00  0 0.00 0.02 0.12 0.30
#&gt; TCGA.SP.A6QD.01     2  0.3294    -0.2390 0.00 0.66  0 0.00 0.00 0.00 0.34
#&gt; TCGA.QR.A6GT.01     2  0.1363     0.4236 0.00 0.94  0 0.00 0.00 0.02 0.04
#&gt; TCGA.QR.A70P.01     2  0.3047    -0.0359 0.00 0.72  0 0.00 0.00 0.00 0.28
#&gt; TCGA.QR.A70I.01     1  0.5429     0.4992 0.54 0.00  0 0.00 0.04 0.10 0.32
#&gt; TCGA.S7.A7WP.01     1  0.1006     0.8136 0.96 0.00  0 0.00 0.00 0.02 0.02
#&gt; TCGA.TT.A6YO.01     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.RM.A68T.01     4  0.1363     0.8758 0.00 0.00  0 0.94 0.00 0.04 0.02
#&gt; TCGA.WB.A81E.01     4  0.4001     0.7793 0.00 0.00  0 0.74 0.02 0.18 0.06
#&gt; TCGA.QR.A6GU.01     2  0.3413    -0.3662 0.00 0.62  0 0.00 0.00 0.00 0.38
#&gt; TCGA.RW.A68F.01     2  0.4264     0.1362 0.00 0.62  0 0.00 0.00 0.32 0.06
#&gt; TCGA.QR.A705.01     4  0.3494     0.8147 0.00 0.00  0 0.80 0.02 0.12 0.06
#&gt; TCGA.S7.A7WO.01     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6ZZ.01     1  0.0000     0.8249 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.P7.A5NX.01     6  0.4981     0.0000 0.00 0.16  0 0.06 0.04 0.70 0.04
#&gt; TCGA.P8.A6RX.01     1  0.3404     0.7423 0.82 0.00  0 0.00 0.06 0.04 0.08
</code></pre>

<script>
$('#tab-node-02-get-classes-6-a').parent().next().next().hide();
$('#tab-node-02-get-classes-6-a').click(function(){
  $('#tab-node-02-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-7'>
<p><a id='tab-node-02-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6   p7   p8
#&gt; TCGA.QR.A6H6.01     7  0.3142     0.7865 0.00 0.36  0 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.QR.A6GZ.01     1  0.1091     0.7934 0.94 0.00  0 0.00 0.00 0.00 0.00 0.06
#&gt; TCGA.QR.A7IP.01     7  0.4575     0.4927 0.00 0.22  0 0.00 0.02 0.00 0.64 0.12
#&gt; TCGA.W2.A7H7.01     7  0.3015     0.7582 0.00 0.32  0 0.00 0.00 0.00 0.68 0.00
#&gt; TCGA.QR.A6H0.01     4  0.0471     0.8867 0.00 0.00  0 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.P8.A5KC.11     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.11     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RM.A68W.01     4  0.0471     0.8902 0.00 0.00  0 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.QT.A5XJ.01     5  0.0471     0.0000 0.00 0.00  0 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.P8.A5KD.11     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70D.01     7  0.4199     0.5251 0.00 0.42  0 0.00 0.00 0.06 0.52 0.00
#&gt; TCGA.WB.A80P.01     2  0.4165     0.4006 0.00 0.64  0 0.00 0.00 0.10 0.26 0.00
#&gt; TCGA.RW.A7CZ.01     2  0.4391    -0.0418 0.00 0.50  0 0.00 0.00 0.08 0.42 0.00
#&gt; TCGA.SR.A6MX.01     2  0.0808     0.4678 0.00 0.96  0 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.WB.A822.01     7  0.3142     0.7773 0.00 0.36  0 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.SR.A6MX.05     2  0.0808     0.4678 0.00 0.96  0 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.RW.A680.01     2  0.3970     0.4090 0.00 0.68  0 0.00 0.00 0.10 0.22 0.00
#&gt; TCGA.QR.A6H3.01     4  0.0000     0.8934 0.00 0.00  0 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.06     2  0.0808     0.4678 0.00 0.96  0 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.QR.A703.01     1  0.0471     0.8090 0.98 0.00  0 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.XG.A823.01     7  0.2852     0.7889 0.00 0.28  0 0.00 0.00 0.00 0.72 0.00
#&gt; TCGA.WB.A81G.01     2  0.3729    -0.3075 0.00 0.52  0 0.00 0.00 0.02 0.46 0.00
#&gt; TCGA.WB.A814.01     1  0.2132     0.7180 0.88 0.00  0 0.00 0.00 0.00 0.04 0.08
#&gt; TCGA.QR.A70Q.01     4  0.2265     0.8672 0.00 0.00  0 0.88 0.00 0.02 0.02 0.08
#&gt; TCGA.SP.A6QG.01     8  0.5305     0.7002 0.28 0.00  0 0.00 0.02 0.00 0.20 0.50
#&gt; TCGA.SP.A6QD.01     7  0.2938     0.8048 0.00 0.30  0 0.00 0.00 0.00 0.70 0.00
#&gt; TCGA.QR.A6GT.01     2  0.4433     0.1532 0.00 0.56  0 0.00 0.00 0.10 0.34 0.00
#&gt; TCGA.QR.A70P.01     7  0.3658     0.6831 0.00 0.40  0 0.00 0.00 0.02 0.58 0.00
#&gt; TCGA.QR.A70I.01     8  0.5035     0.6519 0.36 0.00  0 0.00 0.02 0.00 0.12 0.50
#&gt; TCGA.S7.A7WP.01     1  0.0471     0.8103 0.98 0.00  0 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.TT.A6YO.01     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RM.A68T.01     4  0.0000     0.8934 0.00 0.00  0 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81E.01     4  0.4744     0.7481 0.00 0.00  0 0.70 0.02 0.08 0.08 0.12
#&gt; TCGA.QR.A6GU.01     7  0.2938     0.8048 0.00 0.30  0 0.00 0.00 0.00 0.70 0.00
#&gt; TCGA.RW.A68F.01     2  0.5259     0.1406 0.00 0.38  0 0.00 0.00 0.30 0.32 0.00
#&gt; TCGA.QR.A705.01     4  0.4077     0.8076 0.00 0.00  0 0.76 0.02 0.04 0.10 0.08
#&gt; TCGA.S7.A7WO.01     3  0.0000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6ZZ.01     1  0.0471     0.8103 0.98 0.00  0 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.P7.A5NX.01     6  0.0941     0.0000 0.00 0.00  0 0.02 0.00 0.96 0.02 0.00
#&gt; TCGA.P8.A6RX.01     1  0.5183     0.1561 0.52 0.00  0 0.00 0.00 0.08 0.06 0.34
</code></pre>

<script>
$('#tab-node-02-get-classes-7-a').parent().next().next().hide();
$('#tab-node-02-get-classes-7-a').click(function(){
  $('#tab-node-02-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-02-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-02-consensus-heatmap'>
<ul>
<li><a href='#tab-node-02-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-02-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-02-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-02-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-02-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-02-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-02-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-02-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-02-membership-heatmap'>
<ul>
<li><a href='#tab-node-02-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-02-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-02-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-02-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-02-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-02-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-02-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-1-1.png" alt="plot of chunk tab-node-02-membership-heatmap-1"/></p>

</div>
<div id='tab-node-02-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-2-1.png" alt="plot of chunk tab-node-02-membership-heatmap-2"/></p>

</div>
<div id='tab-node-02-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-3-1.png" alt="plot of chunk tab-node-02-membership-heatmap-3"/></p>

</div>
<div id='tab-node-02-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-4-1.png" alt="plot of chunk tab-node-02-membership-heatmap-4"/></p>

</div>
<div id='tab-node-02-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-5-1.png" alt="plot of chunk tab-node-02-membership-heatmap-5"/></p>

</div>
<div id='tab-node-02-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-6-1.png" alt="plot of chunk tab-node-02-membership-heatmap-6"/></p>

</div>
<div id='tab-node-02-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-7-1.png" alt="plot of chunk tab-node-02-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-02-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-02-get-signatures'>
<ul>
<li><a href='#tab-node-02-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-02-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-02-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-02-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-02-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-02-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-02-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-1-1.png" alt="plot of chunk tab-node-02-get-signatures-1"/></p>

</div>
<div id='tab-node-02-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-2-1.png" alt="plot of chunk tab-node-02-get-signatures-2"/></p>

</div>
<div id='tab-node-02-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-3-1.png" alt="plot of chunk tab-node-02-get-signatures-3"/></p>

</div>
<div id='tab-node-02-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-4-1.png" alt="plot of chunk tab-node-02-get-signatures-4"/></p>

</div>
<div id='tab-node-02-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-5-1.png" alt="plot of chunk tab-node-02-get-signatures-5"/></p>

</div>
<div id='tab-node-02-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-6-1.png" alt="plot of chunk tab-node-02-get-signatures-6"/></p>

</div>
<div id='tab-node-02-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-7-1.png" alt="plot of chunk tab-node-02-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-02-signature_compare](figure_cola/node-02-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-02-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-02-dimension-reduction'>
<ul>
<li><a href='#tab-node-02-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-02-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-02-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-02-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-02-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-02-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-02-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-1-1.png" alt="plot of chunk tab-node-02-dimension-reduction-1"/></p>

</div>
<div id='tab-node-02-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-2-1.png" alt="plot of chunk tab-node-02-dimension-reduction-2"/></p>

</div>
<div id='tab-node-02-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-3-1.png" alt="plot of chunk tab-node-02-dimension-reduction-3"/></p>

</div>
<div id='tab-node-02-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-4-1.png" alt="plot of chunk tab-node-02-dimension-reduction-4"/></p>

</div>
<div id='tab-node-02-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-5-1.png" alt="plot of chunk tab-node-02-dimension-reduction-5"/></p>

</div>
<div id='tab-node-02-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-6-1.png" alt="plot of chunk tab-node-02-dimension-reduction-6"/></p>

</div>
<div id='tab-node-02-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-7-1.png" alt="plot of chunk tab-node-02-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-02-collect-classes](figure_cola/node-02-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node022


Parent node: [Node02](#Node02).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0311-leaf
        ,
                Node0312-leaf
        ,
                Node0313-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0411-leaf
        ,
                Node0412-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["022"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 19 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-022-collect-plots](figure_cola/node-022-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-022-select-partition-number](figure_cola/node-022-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.4567 0.544   0.544
#> 3 3 0.713           0.983       0.949         0.4644 0.766   0.570
#> 4 4 0.842           0.913       0.848         0.1304 0.947   0.830
#> 5 5 0.784           0.696       0.816         0.0537 0.930   0.727
#> 6 6 0.819           0.839       0.859         0.0378 0.906   0.556
#> 7 7 0.813           0.809       0.882         0.0379 1.000   1.000
#> 8 8 0.813           0.642       0.797         0.0173 0.971   0.792
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-022-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-022-get-classes'>
<ul>
<li><a href='#tab-node-022-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-022-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-022-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-022-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-022-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-022-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-022-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-022-get-classes-1'>
<p><a id='tab-node-022-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.QR.A6H6.01     1       0          1  1  0
#&gt; TCGA.QR.A7IP.01     1       0          1  1  0
#&gt; TCGA.W2.A7H7.01     1       0          1  1  0
#&gt; TCGA.QT.A5XJ.01     1       0          1  1  0
#&gt; TCGA.QR.A70D.01     1       0          1  1  0
#&gt; TCGA.WB.A80P.01     2       0          1  0  1
#&gt; TCGA.RW.A7CZ.01     1       0          1  1  0
#&gt; TCGA.SR.A6MX.01     2       0          1  0  1
#&gt; TCGA.WB.A822.01     1       0          1  1  0
#&gt; TCGA.SR.A6MX.05     2       0          1  0  1
#&gt; TCGA.RW.A680.01     2       0          1  0  1
#&gt; TCGA.SR.A6MX.06     2       0          1  0  1
#&gt; TCGA.XG.A823.01     1       0          1  1  0
#&gt; TCGA.WB.A81G.01     1       0          1  1  0
#&gt; TCGA.SP.A6QD.01     1       0          1  1  0
#&gt; TCGA.QR.A6GT.01     2       0          1  0  1
#&gt; TCGA.QR.A70P.01     1       0          1  1  0
#&gt; TCGA.QR.A6GU.01     1       0          1  1  0
#&gt; TCGA.RW.A68F.01     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-022-get-classes-1-a').parent().next().next().hide();
$('#tab-node-022-get-classes-1-a').click(function(){
  $('#tab-node-022-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-2'>
<p><a id='tab-node-022-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.QR.A6H6.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.QR.A7IP.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     3   0.334      1.000 0.12 0.00 0.88
#&gt; TCGA.QT.A5XJ.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.QR.A70D.01     3   0.334      1.000 0.12 0.00 0.88
#&gt; TCGA.WB.A80P.01     2   0.000      0.945 0.00 1.00 0.00
#&gt; TCGA.RW.A7CZ.01     3   0.334      1.000 0.12 0.00 0.88
#&gt; TCGA.SR.A6MX.01     2   0.334      0.945 0.00 0.88 0.12
#&gt; TCGA.WB.A822.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.SR.A6MX.05     2   0.334      0.945 0.00 0.88 0.12
#&gt; TCGA.RW.A680.01     2   0.000      0.945 0.00 1.00 0.00
#&gt; TCGA.SR.A6MX.06     2   0.334      0.945 0.00 0.88 0.12
#&gt; TCGA.XG.A823.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.WB.A81G.01     3   0.334      1.000 0.12 0.00 0.88
#&gt; TCGA.SP.A6QD.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.QR.A6GT.01     2   0.000      0.945 0.00 1.00 0.00
#&gt; TCGA.QR.A70P.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.QR.A6GU.01     1   0.000      1.000 1.00 0.00 0.00
#&gt; TCGA.RW.A68F.01     3   0.334      1.000 0.12 0.00 0.88
</code></pre>

<script>
$('#tab-node-022-get-classes-2-a').parent().next().next().hide();
$('#tab-node-022-get-classes-2-a').click(function(){
  $('#tab-node-022-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-3'>
<p><a id='tab-node-022-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.QR.A6H6.01     1  0.4406      0.823 0.70 0.30 0.00 0.00
#&gt; TCGA.QR.A7IP.01     1  0.4406      0.823 0.70 0.30 0.00 0.00
#&gt; TCGA.W2.A7H7.01     3  0.1211      0.964 0.00 0.04 0.96 0.00
#&gt; TCGA.QT.A5XJ.01     1  0.4406      0.823 0.70 0.30 0.00 0.00
#&gt; TCGA.QR.A70D.01     3  0.0000      0.984 0.00 0.00 1.00 0.00
#&gt; TCGA.WB.A80P.01     2  0.4977      1.000 0.00 0.54 0.00 0.46
#&gt; TCGA.RW.A7CZ.01     3  0.0000      0.984 0.00 0.00 1.00 0.00
#&gt; TCGA.SR.A6MX.01     4  0.0000      1.000 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A822.01     1  0.0000      0.812 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.05     4  0.0000      1.000 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A680.01     2  0.4977      1.000 0.00 0.54 0.00 0.46
#&gt; TCGA.SR.A6MX.06     4  0.0000      1.000 0.00 0.00 0.00 1.00
#&gt; TCGA.XG.A823.01     1  0.2647      0.762 0.88 0.12 0.00 0.00
#&gt; TCGA.WB.A81G.01     3  0.0000      0.984 0.00 0.00 1.00 0.00
#&gt; TCGA.SP.A6QD.01     1  0.0707      0.808 0.98 0.02 0.00 0.00
#&gt; TCGA.QR.A6GT.01     2  0.4977      1.000 0.00 0.54 0.00 0.46
#&gt; TCGA.QR.A70P.01     1  0.4406      0.823 0.70 0.30 0.00 0.00
#&gt; TCGA.QR.A6GU.01     1  0.2011      0.785 0.92 0.08 0.00 0.00
#&gt; TCGA.RW.A68F.01     3  0.1211      0.966 0.00 0.04 0.96 0.00
</code></pre>

<script>
$('#tab-node-022-get-classes-3-a').parent().next().next().hide();
$('#tab-node-022-get-classes-3-a').click(function(){
  $('#tab-node-022-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-4'>
<p><a id='tab-node-022-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.QR.A6H6.01     1   0.000      0.624 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A7IP.01     1   0.000      0.624 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     3   0.000      0.933 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QT.A5XJ.01     1   0.000      0.624 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70D.01     3   0.000      0.933 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A80P.01     2   0.000      0.949 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     3   0.000      0.933 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SR.A6MX.01     4   0.352      0.966 0.00 0.14 0.00 0.82 0.04
#&gt; TCGA.WB.A822.01     1   0.426     -0.662 0.56 0.00 0.00 0.00 0.44
#&gt; TCGA.SR.A6MX.05     4   0.252      0.983 0.00 0.14 0.00 0.86 0.00
#&gt; TCGA.RW.A680.01     2   0.141      0.932 0.00 0.94 0.00 0.00 0.06
#&gt; TCGA.SR.A6MX.06     4   0.252      0.983 0.00 0.14 0.00 0.86 0.00
#&gt; TCGA.XG.A823.01     5   0.426      1.000 0.44 0.00 0.00 0.00 0.56
#&gt; TCGA.WB.A81G.01     3   0.000      0.933 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SP.A6QD.01     1   0.429     -0.718 0.54 0.00 0.00 0.00 0.46
#&gt; TCGA.QR.A6GT.01     2   0.141      0.932 0.00 0.94 0.00 0.00 0.06
#&gt; TCGA.QR.A70P.01     1   0.202      0.563 0.90 0.00 0.00 0.10 0.00
#&gt; TCGA.QR.A6GU.01     5   0.426      1.000 0.44 0.00 0.00 0.00 0.56
#&gt; TCGA.RW.A68F.01     3   0.464      0.698 0.00 0.00 0.68 0.04 0.28
</code></pre>

<script>
$('#tab-node-022-get-classes-4-a').parent().next().next().hide();
$('#tab-node-022-get-classes-4-a').click(function(){
  $('#tab-node-022-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-5'>
<p><a id='tab-node-022-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.QR.A6H6.01     1   0.000      0.933 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A7IP.01     1   0.000      0.933 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     3   0.000      0.901 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XJ.01     1   0.000      0.933 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70D.01     3   0.279      0.662 0.00 0.00 0.80 0.00 0.20 0.00
#&gt; TCGA.WB.A80P.01     2   0.000      0.860 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     3   0.000      0.901 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.01     4   0.109      0.967 0.00 0.00 0.00 0.96 0.02 0.02
#&gt; TCGA.WB.A822.01     5   0.385      0.857 0.46 0.00 0.00 0.00 0.54 0.00
#&gt; TCGA.SR.A6MX.05     4   0.000      0.984 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.RW.A680.01     2   0.247      0.828 0.00 0.88 0.00 0.00 0.08 0.04
#&gt; TCGA.SR.A6MX.06     4   0.000      0.984 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.XG.A823.01     5   0.365      0.912 0.36 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.WB.A81G.01     3   0.000      0.901 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QD.01     5   0.380      0.903 0.42 0.00 0.00 0.00 0.58 0.00
#&gt; TCGA.QR.A6GT.01     2   0.347      0.788 0.00 0.80 0.00 0.00 0.06 0.14
#&gt; TCGA.QR.A70P.01     1   0.245      0.785 0.84 0.00 0.00 0.00 0.00 0.16
#&gt; TCGA.QR.A6GU.01     5   0.365      0.912 0.36 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.RW.A68F.01     6   0.365      0.000 0.00 0.00 0.36 0.00 0.00 0.64
</code></pre>

<script>
$('#tab-node-022-get-classes-5-a').parent().next().next().hide();
$('#tab-node-022-get-classes-5-a').click(function(){
  $('#tab-node-022-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-6'>
<p><a id='tab-node-022-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.QR.A6H6.01     1  0.0504      0.893 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A7IP.01     1  0.0000      0.898 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7H7.01     3  0.0863      0.844 0.00 0.00 0.96 0.00 0.04 0.00 0.00
#&gt; TCGA.QT.A5XJ.01     1  0.0000      0.898 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70D.01     3  0.3413      0.529 0.00 0.00 0.62 0.38 0.00 0.00 0.00
#&gt; TCGA.WB.A80P.01     2  0.0000      0.806 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A7CZ.01     3  0.0000      0.854 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.01     7  0.0504      0.983 0.00 0.00 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.WB.A822.01     5  0.2945      0.905 0.26 0.00 0.00 0.00 0.74 0.00 0.00
#&gt; TCGA.SR.A6MX.05     7  0.0000      0.991 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A680.01     2  0.3656      0.756 0.00 0.80 0.00 0.08 0.08 0.04 0.00
#&gt; TCGA.SR.A6MX.06     7  0.0000      0.991 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.XG.A823.01     5  0.4001      0.879 0.18 0.00 0.00 0.06 0.74 0.02 0.00
#&gt; TCGA.WB.A81G.01     3  0.0000      0.854 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QD.01     5  0.2708      0.933 0.22 0.00 0.00 0.00 0.78 0.00 0.00
#&gt; TCGA.QR.A6GT.01     2  0.3526      0.734 0.00 0.76 0.00 0.18 0.06 0.00 0.00
#&gt; TCGA.QR.A70P.01     1  0.3139      0.684 0.70 0.00 0.00 0.30 0.00 0.00 0.00
#&gt; TCGA.QR.A6GU.01     5  0.2572      0.932 0.20 0.00 0.00 0.00 0.80 0.00 0.00
#&gt; TCGA.RW.A68F.01     6  0.1671      0.000 0.00 0.00 0.10 0.00 0.00 0.90 0.00
</code></pre>

<script>
$('#tab-node-022-get-classes-6-a').parent().next().next().hide();
$('#tab-node-022-get-classes-6-a').click(function(){
  $('#tab-node-022-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-7'>
<p><a id='tab-node-022-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.QR.A6H6.01     1  0.5970      0.845 0.44 0.00 0.00 0.02 0.18 0.04 0.00 0.32
#&gt; TCGA.QR.A7IP.01     1  0.4943      0.925 0.48 0.00 0.00 0.00 0.18 0.00 0.00 0.34
#&gt; TCGA.W2.A7H7.01     3  0.2623      0.705 0.00 0.00 0.84 0.10 0.00 0.00 0.00 0.06
#&gt; TCGA.QT.A5XJ.01     1  0.4943      0.925 0.48 0.00 0.00 0.00 0.18 0.00 0.00 0.34
#&gt; TCGA.QR.A70D.01     3  0.4698      0.290 0.44 0.00 0.44 0.12 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80P.01     2  0.3941      0.249 0.04 0.68 0.00 0.26 0.00 0.00 0.00 0.02
#&gt; TCGA.RW.A7CZ.01     3  0.0000      0.755 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.01     7  0.2350      0.870 0.00 0.00 0.00 0.00 0.00 0.04 0.86 0.10
#&gt; TCGA.WB.A822.01     5  0.1557      0.877 0.02 0.00 0.00 0.00 0.92 0.00 0.00 0.06
#&gt; TCGA.SR.A6MX.05     7  0.0000      0.938 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A680.01     2  0.0000      0.460 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MX.06     7  0.0000      0.938 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.XG.A823.01     5  0.1804      0.849 0.02 0.00 0.00 0.08 0.90 0.00 0.00 0.00
#&gt; TCGA.WB.A81G.01     3  0.0000      0.755 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QD.01     5  0.0808      0.908 0.00 0.00 0.00 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.QR.A6GT.01     4  0.3015      0.000 0.00 0.32 0.00 0.68 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70P.01     8  0.2267      0.000 0.00 0.00 0.00 0.00 0.18 0.00 0.00 0.82
#&gt; TCGA.QR.A6GU.01     5  0.0000      0.904 0.00 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A68F.01     6  0.1341      0.000 0.00 0.00 0.08 0.00 0.00 0.92 0.00 0.00
</code></pre>

<script>
$('#tab-node-022-get-classes-7-a').parent().next().next().hide();
$('#tab-node-022-get-classes-7-a').click(function(){
  $('#tab-node-022-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-022-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-022-consensus-heatmap'>
<ul>
<li><a href='#tab-node-022-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-022-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-022-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-022-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-022-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-022-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-022-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-022-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-022-membership-heatmap'>
<ul>
<li><a href='#tab-node-022-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-022-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-022-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-022-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-022-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-022-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-022-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-1-1.png" alt="plot of chunk tab-node-022-membership-heatmap-1"/></p>

</div>
<div id='tab-node-022-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-2-1.png" alt="plot of chunk tab-node-022-membership-heatmap-2"/></p>

</div>
<div id='tab-node-022-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-3-1.png" alt="plot of chunk tab-node-022-membership-heatmap-3"/></p>

</div>
<div id='tab-node-022-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-4-1.png" alt="plot of chunk tab-node-022-membership-heatmap-4"/></p>

</div>
<div id='tab-node-022-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-5-1.png" alt="plot of chunk tab-node-022-membership-heatmap-5"/></p>

</div>
<div id='tab-node-022-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-6-1.png" alt="plot of chunk tab-node-022-membership-heatmap-6"/></p>

</div>
<div id='tab-node-022-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-7-1.png" alt="plot of chunk tab-node-022-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-022-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-022-get-signatures'>
<ul>
<li><a href='#tab-node-022-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-022-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-022-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-022-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-022-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-022-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-022-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-1-1.png" alt="plot of chunk tab-node-022-get-signatures-1"/></p>

</div>
<div id='tab-node-022-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-2-1.png" alt="plot of chunk tab-node-022-get-signatures-2"/></p>

</div>
<div id='tab-node-022-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-3-1.png" alt="plot of chunk tab-node-022-get-signatures-3"/></p>

</div>
<div id='tab-node-022-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-4-1.png" alt="plot of chunk tab-node-022-get-signatures-4"/></p>

</div>
<div id='tab-node-022-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-5-1.png" alt="plot of chunk tab-node-022-get-signatures-5"/></p>

</div>
<div id='tab-node-022-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-6-1.png" alt="plot of chunk tab-node-022-get-signatures-6"/></p>

</div>
<div id='tab-node-022-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-7-1.png" alt="plot of chunk tab-node-022-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-022-signature_compare](figure_cola/node-022-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-022-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-022-dimension-reduction'>
<ul>
<li><a href='#tab-node-022-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-022-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-022-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-022-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-022-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-022-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-022-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-1-1.png" alt="plot of chunk tab-node-022-dimension-reduction-1"/></p>

</div>
<div id='tab-node-022-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-2-1.png" alt="plot of chunk tab-node-022-dimension-reduction-2"/></p>

</div>
<div id='tab-node-022-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-3-1.png" alt="plot of chunk tab-node-022-dimension-reduction-3"/></p>

</div>
<div id='tab-node-022-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-4-1.png" alt="plot of chunk tab-node-022-dimension-reduction-4"/></p>

</div>
<div id='tab-node-022-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-5-1.png" alt="plot of chunk tab-node-022-dimension-reduction-5"/></p>

</div>
<div id='tab-node-022-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-6-1.png" alt="plot of chunk tab-node-022-dimension-reduction-6"/></p>

</div>
<div id='tab-node-022-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-7-1.png" alt="plot of chunk tab-node-022-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-022-collect-classes](figure_cola/node-022-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node03


Parent node: [Node0](#Node0).
Child nodes: 
                Node011-leaf
        ,
                [Node012](#Node012)
        ,
                [Node013](#Node013)
        ,
                Node021-leaf
        ,
                [Node022](#Node022)
        ,
                Node023-leaf
        ,
                Node024-leaf
        ,
                [Node031](#Node031)
        ,
                [Node032](#Node032)
        ,
                Node033-leaf
        ,
                [Node041](#Node041)
        ,
                Node042-leaf
        ,
                Node043-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["03"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 49 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-03-collect-plots](figure_cola/node-03-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-03-select-partition-number](figure_cola/node-03-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           0.978       0.991         0.4713 0.526   0.526
#> 3 3 1.000           0.994       0.997         0.3532 0.651   0.437
#> 4 4 0.718           0.729       0.686         0.1340 0.791   0.490
#> 5 5 0.687           0.727       0.821         0.0444 0.939   0.785
#> 6 6 0.697           0.424       0.632         0.0560 0.824   0.442
#> 7 7 0.716           0.580       0.759         0.0255 0.875   0.491
#> 8 8 0.743           0.570       0.753         0.0174 0.938   0.713
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-03-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-03-get-classes'>
<ul>
<li><a href='#tab-node-03-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-03-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-03-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-03-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-03-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-03-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-03-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-03-get-classes-1'>
<p><a id='tab-node-03-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.WB.A81K.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70O.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.QR.A700.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70C.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80L.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.WB.A81P.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A68A.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.WB.A80K.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QT.A5XM.01     1   0.327      0.934 0.94 0.06
#&gt; TCGA.QR.A70X.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.WB.A81H.01     2   0.943      0.434 0.36 0.64
#&gt; TCGA.SR.A6MV.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.SR.A6MP.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.PR.A5PH.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.QR.A6GR.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A686.06     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A684.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.SQ.A6I4.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A821.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.SR.A6MZ.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.SP.A6QK.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.S7.A7WU.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A820.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81F.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81Q.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.TT.A6YJ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A819.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WL.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A817.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A7D0.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.WB.A80Q.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MQ.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.RW.A685.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SP.A6QC.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QR.A70G.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81V.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81N.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A80O.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.QT.A5XN.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A816.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.P7.A5NY.05     2   0.000      0.979 0.00 1.00
#&gt; TCGA.W2.A7H5.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.RX.A8JQ.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.RW.A686.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.WB.A81I.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.W2.A7HE.01     2   0.000      0.979 0.00 1.00
#&gt; TCGA.QR.A702.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.S7.A7WN.01     1   0.000      0.998 1.00 0.00
#&gt; TCGA.SR.A6MU.01     2   0.000      0.979 0.00 1.00
</code></pre>

<script>
$('#tab-node-03-get-classes-1-a').parent().next().next().hide();
$('#tab-node-03-get-classes-1-a').click(function(){
  $('#tab-node-03-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-2'>
<p><a id='tab-node-03-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1   p2   p3
#&gt; TCGA.WB.A81K.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.QR.A70O.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.QR.A700.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.QR.A70C.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A80L.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A81P.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.RW.A68A.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A80K.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.QT.A5XM.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.QR.A70X.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A81H.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.SR.A6MV.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.SR.A6MP.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.PR.A5PH.01     2   0.369      0.837  0 0.86 0.14
#&gt; TCGA.QR.A6GR.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.RW.A686.06     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.RW.A684.01     3   0.000      1.000  0 0.00 1.00
#&gt; TCGA.SQ.A6I4.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A821.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.SR.A6MZ.01     3   0.000      1.000  0 0.00 1.00
#&gt; TCGA.SP.A6QK.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.S7.A7WU.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A820.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A81F.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A81Q.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A819.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.S7.A7WL.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A817.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.RW.A7D0.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A80Q.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.SR.A6MQ.01     3   0.000      1.000  0 0.00 1.00
#&gt; TCGA.RW.A685.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.SP.A6QC.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.QR.A70G.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A81V.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A81N.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A80O.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.QT.A5XN.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A816.01     3   0.000      1.000  0 0.00 1.00
#&gt; TCGA.P7.A5NY.05     3   0.000      1.000  0 0.00 1.00
#&gt; TCGA.W2.A7H5.01     3   0.000      1.000  0 0.00 1.00
#&gt; TCGA.RX.A8JQ.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.RW.A686.01     2   0.000      0.993  0 1.00 0.00
#&gt; TCGA.WB.A81I.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.W2.A7HE.01     3   0.000      1.000  0 0.00 1.00
#&gt; TCGA.QR.A702.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.S7.A7WN.01     1   0.000      1.000  1 0.00 0.00
#&gt; TCGA.SR.A6MU.01     3   0.000      1.000  0 0.00 1.00
</code></pre>

<script>
$('#tab-node-03-get-classes-2-a').parent().next().next().hide();
$('#tab-node-03-get-classes-2-a').click(function(){
  $('#tab-node-03-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-3'>
<p><a id='tab-node-03-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.WB.A81K.01     2   0.491    -0.0849 0.00 0.58 0.00 0.42
#&gt; TCGA.QR.A70O.01     2   0.164     0.7903 0.00 0.94 0.00 0.06
#&gt; TCGA.QR.A700.01     1   0.265     0.8639 0.88 0.00 0.00 0.12
#&gt; TCGA.QR.A70C.01     4   0.471     0.5714 0.00 0.36 0.00 0.64
#&gt; TCGA.WB.A80L.01     2   0.000     0.8226 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A81P.01     1   0.428     0.9047 0.72 0.00 0.00 0.28
#&gt; TCGA.RW.A68A.01     2   0.164     0.7903 0.00 0.94 0.00 0.06
#&gt; TCGA.WB.A80K.01     4   0.479     0.5565 0.00 0.38 0.00 0.62
#&gt; TCGA.QT.A5XM.01     2   0.452     0.3173 0.00 0.68 0.00 0.32
#&gt; TCGA.QR.A70X.01     2   0.000     0.8226 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A81H.01     2   0.452     0.3173 0.00 0.68 0.00 0.32
#&gt; TCGA.SR.A6MV.01     2   0.000     0.8226 0.00 1.00 0.00 0.00
#&gt; TCGA.SR.A6MP.01     4   0.361     0.2830 0.20 0.00 0.00 0.80
#&gt; TCGA.PR.A5PH.01     2   0.265     0.7127 0.00 0.88 0.12 0.00
#&gt; TCGA.QR.A6GR.01     1   0.452     0.9012 0.68 0.00 0.00 0.32
#&gt; TCGA.RW.A686.06     4   0.471     0.5714 0.00 0.36 0.00 0.64
#&gt; TCGA.RW.A684.01     3   0.000     1.0000 0.00 0.00 1.00 0.00
#&gt; TCGA.SQ.A6I4.01     4   0.485     0.5529 0.00 0.40 0.00 0.60
#&gt; TCGA.WB.A821.01     2   0.000     0.8226 0.00 1.00 0.00 0.00
#&gt; TCGA.SR.A6MZ.01     3   0.000     1.0000 0.00 0.00 1.00 0.00
#&gt; TCGA.SP.A6QK.01     2   0.000     0.8226 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     4   0.265     0.5086 0.12 0.00 0.00 0.88
#&gt; TCGA.WB.A820.01     1   0.441     0.9071 0.70 0.00 0.00 0.30
#&gt; TCGA.WB.A81F.01     1   0.452     0.9012 0.68 0.00 0.00 0.32
#&gt; TCGA.WB.A81Q.01     1   0.340     0.8626 0.82 0.00 0.00 0.18
#&gt; TCGA.TT.A6YJ.01     1   0.292     0.8546 0.86 0.00 0.00 0.14
#&gt; TCGA.WB.A819.01     1   0.428     0.9047 0.72 0.00 0.00 0.28
#&gt; TCGA.S7.A7WL.01     1   0.380     0.9044 0.78 0.00 0.00 0.22
#&gt; TCGA.WB.A817.01     4   0.491     0.5257 0.00 0.42 0.00 0.58
#&gt; TCGA.RW.A7D0.01     2   0.000     0.8226 0.00 1.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     4   0.234     0.5226 0.10 0.00 0.00 0.90
#&gt; TCGA.SR.A6MQ.01     3   0.000     1.0000 0.00 0.00 1.00 0.00
#&gt; TCGA.RW.A685.01     4   0.234     0.4926 0.10 0.00 0.00 0.90
#&gt; TCGA.SP.A6QC.01     4   0.485     0.5529 0.00 0.40 0.00 0.60
#&gt; TCGA.QR.A70G.01     1   0.428     0.9047 0.72 0.00 0.00 0.28
#&gt; TCGA.WB.A81V.01     4   0.491     0.5257 0.00 0.42 0.00 0.58
#&gt; TCGA.WB.A81N.01     4   0.491     0.5257 0.00 0.42 0.00 0.58
#&gt; TCGA.WB.A80O.01     4   0.234     0.4926 0.10 0.00 0.00 0.90
#&gt; TCGA.QT.A5XN.01     1   0.292     0.8546 0.86 0.00 0.00 0.14
#&gt; TCGA.WB.A816.01     3   0.000     1.0000 0.00 0.00 1.00 0.00
#&gt; TCGA.P7.A5NY.05     3   0.000     1.0000 0.00 0.00 1.00 0.00
#&gt; TCGA.W2.A7H5.01     3   0.000     1.0000 0.00 0.00 1.00 0.00
#&gt; TCGA.RX.A8JQ.01     4   0.361     0.2830 0.20 0.00 0.00 0.80
#&gt; TCGA.RW.A686.01     4   0.479     0.5565 0.00 0.38 0.00 0.62
#&gt; TCGA.WB.A81I.01     1   0.265     0.8639 0.88 0.00 0.00 0.12
#&gt; TCGA.W2.A7HE.01     3   0.000     1.0000 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A702.01     1   0.265     0.8639 0.88 0.00 0.00 0.12
#&gt; TCGA.S7.A7WN.01     1   0.441     0.9071 0.70 0.00 0.00 0.30
#&gt; TCGA.SR.A6MU.01     3   0.000     1.0000 0.00 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-3-a').parent().next().next().hide();
$('#tab-node-03-get-classes-3-a').click(function(){
  $('#tab-node-03-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-4'>
<p><a id='tab-node-03-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.WB.A81K.01     4  0.3684      0.392 0.00 0.28 0.00 0.72 0.00
#&gt; TCGA.QR.A70O.01     2  0.5555      0.758 0.22 0.64 0.00 0.14 0.00
#&gt; TCGA.QR.A700.01     5  0.4558      0.740 0.18 0.08 0.00 0.00 0.74
#&gt; TCGA.QR.A70C.01     4  0.1732      0.647 0.08 0.00 0.00 0.92 0.00
#&gt; TCGA.WB.A80L.01     2  0.3274      0.906 0.00 0.78 0.00 0.22 0.00
#&gt; TCGA.WB.A81P.01     5  0.0609      0.831 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.RW.A68A.01     2  0.5791      0.731 0.26 0.60 0.00 0.14 0.00
#&gt; TCGA.WB.A80K.01     4  0.1732      0.647 0.08 0.00 0.00 0.92 0.00
#&gt; TCGA.QT.A5XM.01     4  0.3796      0.355 0.00 0.30 0.00 0.70 0.00
#&gt; TCGA.QR.A70X.01     2  0.3274      0.906 0.00 0.78 0.00 0.22 0.00
#&gt; TCGA.WB.A81H.01     4  0.3796      0.355 0.00 0.30 0.00 0.70 0.00
#&gt; TCGA.SR.A6MV.01     2  0.3109      0.916 0.00 0.80 0.00 0.20 0.00
#&gt; TCGA.SR.A6MP.01     4  0.4302      0.272 0.00 0.00 0.00 0.52 0.48
#&gt; TCGA.PR.A5PH.01     2  0.2929      0.912 0.00 0.82 0.00 0.18 0.00
#&gt; TCGA.QR.A6GR.01     5  0.0609      0.831 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.RW.A686.06     4  0.3421      0.649 0.08 0.00 0.00 0.84 0.08
#&gt; TCGA.RW.A684.01     3  0.0000      0.993 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.01     4  0.2754      0.654 0.00 0.08 0.00 0.88 0.04
#&gt; TCGA.WB.A821.01     2  0.3109      0.916 0.00 0.80 0.00 0.20 0.00
#&gt; TCGA.SR.A6MZ.01     3  0.0000      0.993 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     2  0.2929      0.912 0.00 0.82 0.00 0.18 0.00
#&gt; TCGA.S7.A7WU.01     4  0.5498      0.463 0.08 0.00 0.00 0.58 0.34
#&gt; TCGA.WB.A820.01     5  0.0000      0.833 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A81F.01     5  0.0609      0.831 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.WB.A81Q.01     5  0.5925      0.571 0.40 0.06 0.00 0.02 0.52
#&gt; TCGA.TT.A6YJ.01     5  0.4262      0.614 0.44 0.00 0.00 0.00 0.56
#&gt; TCGA.WB.A819.01     5  0.0609      0.831 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.S7.A7WL.01     5  0.0000      0.833 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.WB.A817.01     4  0.2020      0.621 0.00 0.10 0.00 0.90 0.00
#&gt; TCGA.RW.A7D0.01     2  0.3109      0.916 0.00 0.80 0.00 0.20 0.00
#&gt; TCGA.WB.A80Q.01     4  0.4725      0.596 0.08 0.00 0.00 0.72 0.20
#&gt; TCGA.SR.A6MQ.01     3  0.0000      0.993 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.RW.A685.01     4  0.4227      0.402 0.00 0.00 0.00 0.58 0.42
#&gt; TCGA.SP.A6QC.01     4  0.1732      0.638 0.00 0.08 0.00 0.92 0.00
#&gt; TCGA.QR.A70G.01     5  0.0609      0.831 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.WB.A81V.01     4  0.1732      0.638 0.00 0.08 0.00 0.92 0.00
#&gt; TCGA.WB.A81N.01     4  0.3274      0.498 0.00 0.22 0.00 0.78 0.00
#&gt; TCGA.WB.A80O.01     4  0.4227      0.402 0.00 0.00 0.00 0.58 0.42
#&gt; TCGA.QT.A5XN.01     5  0.4262      0.614 0.44 0.00 0.00 0.00 0.56
#&gt; TCGA.WB.A816.01     3  0.0609      0.989 0.00 0.02 0.98 0.00 0.00
#&gt; TCGA.P7.A5NY.05     3  0.0609      0.989 0.00 0.02 0.98 0.00 0.00
#&gt; TCGA.W2.A7H5.01     3  0.0000      0.993 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     4  0.4302      0.272 0.00 0.00 0.00 0.52 0.48
#&gt; TCGA.RW.A686.01     4  0.1732      0.647 0.08 0.00 0.00 0.92 0.00
#&gt; TCGA.WB.A81I.01     5  0.4558      0.740 0.18 0.08 0.00 0.00 0.74
#&gt; TCGA.W2.A7HE.01     3  0.0609      0.989 0.00 0.02 0.98 0.00 0.00
#&gt; TCGA.QR.A702.01     5  0.4558      0.740 0.18 0.08 0.00 0.00 0.74
#&gt; TCGA.S7.A7WN.01     5  0.0000      0.833 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.SR.A6MU.01     3  0.0000      0.993 0.00 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-4-a').parent().next().next().hide();
$('#tab-node-03-get-classes-4-a').click(function(){
  $('#tab-node-03-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-5'>
<p><a id='tab-node-03-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.WB.A81K.01     2  0.5354      0.398 0.26 0.58 0.00 0.16 0.00 0.00
#&gt; TCGA.QR.A70O.01     2  0.5712      0.363 0.22 0.52 0.00 0.00 0.00 0.26
#&gt; TCGA.QR.A700.01     5  0.2350      0.415 0.02 0.00 0.00 0.10 0.88 0.00
#&gt; TCGA.QR.A70C.01     6  0.6380      0.951 0.24 0.02 0.00 0.30 0.00 0.44
#&gt; TCGA.WB.A80L.01     2  0.0000      0.722 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81P.01     4  0.3869     -0.557 0.00 0.00 0.00 0.50 0.50 0.00
#&gt; TCGA.RW.A68A.01     2  0.5921      0.310 0.30 0.46 0.00 0.00 0.00 0.24
#&gt; TCGA.WB.A80K.01     6  0.6380      0.951 0.24 0.02 0.00 0.30 0.00 0.44
#&gt; TCGA.QT.A5XM.01     2  0.5259      0.429 0.24 0.60 0.00 0.16 0.00 0.00
#&gt; TCGA.QR.A70X.01     2  0.0000      0.722 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81H.01     2  0.5259      0.429 0.24 0.60 0.00 0.16 0.00 0.00
#&gt; TCGA.SR.A6MV.01     2  0.0547      0.718 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.SR.A6MP.01     4  0.0937      0.330 0.00 0.00 0.00 0.96 0.04 0.00
#&gt; TCGA.PR.A5PH.01     2  0.2474      0.668 0.00 0.88 0.04 0.00 0.00 0.08
#&gt; TCGA.QR.A6GR.01     4  0.3864     -0.553 0.00 0.00 0.00 0.52 0.48 0.00
#&gt; TCGA.RW.A686.06     6  0.6441      0.950 0.26 0.02 0.00 0.30 0.00 0.42
#&gt; TCGA.RW.A684.01     3  0.0000      0.992 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.01     4  0.5608     -0.265 0.26 0.20 0.00 0.54 0.00 0.00
#&gt; TCGA.WB.A821.01     2  0.0547      0.718 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.SR.A6MZ.01     3  0.0000      0.992 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     2  0.0547      0.719 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.S7.A7WU.01     4  0.4244      0.133 0.00 0.00 0.00 0.72 0.08 0.20
#&gt; TCGA.WB.A820.01     5  0.4646      0.503 0.00 0.00 0.00 0.46 0.50 0.04
#&gt; TCGA.WB.A81F.01     4  0.3864     -0.553 0.00 0.00 0.00 0.52 0.48 0.00
#&gt; TCGA.WB.A81Q.01     1  0.7645      0.000 0.32 0.00 0.00 0.20 0.26 0.22
#&gt; TCGA.TT.A6YJ.01     5  0.6616     -0.684 0.36 0.00 0.00 0.08 0.44 0.12
#&gt; TCGA.WB.A819.01     5  0.3864      0.489 0.00 0.00 0.00 0.48 0.52 0.00
#&gt; TCGA.S7.A7WL.01     5  0.3706      0.525 0.00 0.00 0.00 0.38 0.62 0.00
#&gt; TCGA.WB.A817.01     4  0.5987     -0.238 0.26 0.30 0.00 0.44 0.00 0.00
#&gt; TCGA.RW.A7D0.01     2  0.0000      0.722 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     6  0.5791      0.832 0.18 0.00 0.00 0.38 0.00 0.44
#&gt; TCGA.SR.A6MQ.01     3  0.0000      0.992 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A685.01     4  0.0547      0.340 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.SP.A6QC.01     4  0.5876     -0.257 0.26 0.26 0.00 0.48 0.00 0.00
#&gt; TCGA.QR.A70G.01     5  0.3864      0.489 0.00 0.00 0.00 0.48 0.52 0.00
#&gt; TCGA.WB.A81V.01     4  0.5876     -0.257 0.26 0.26 0.00 0.48 0.00 0.00
#&gt; TCGA.WB.A81N.01     2  0.5938      0.118 0.26 0.46 0.00 0.28 0.00 0.00
#&gt; TCGA.WB.A80O.01     4  0.0547      0.340 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.QT.A5XN.01     5  0.6616     -0.684 0.36 0.00 0.00 0.08 0.44 0.12
#&gt; TCGA.WB.A816.01     3  0.0547      0.986 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.P7.A5NY.05     3  0.0547      0.986 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.W2.A7H5.01     3  0.0000      0.992 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     4  0.0937      0.330 0.00 0.00 0.00 0.96 0.04 0.00
#&gt; TCGA.RW.A686.01     6  0.6441      0.950 0.26 0.02 0.00 0.30 0.00 0.42
#&gt; TCGA.WB.A81I.01     5  0.2350      0.415 0.02 0.00 0.00 0.10 0.88 0.00
#&gt; TCGA.W2.A7HE.01     3  0.0547      0.986 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.QR.A702.01     5  0.2350      0.415 0.02 0.00 0.00 0.10 0.88 0.00
#&gt; TCGA.S7.A7WN.01     5  0.4646      0.503 0.00 0.00 0.00 0.46 0.50 0.04
#&gt; TCGA.SR.A6MU.01     3  0.0000      0.992 0.00 0.00 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-5-a').parent().next().next().hide();
$('#tab-node-03-get-classes-5-a').click(function(){
  $('#tab-node-03-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-6'>
<p><a id='tab-node-03-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.WB.A81K.01     2  0.5173      0.191 0.00 0.50 0.00 0.00 0.00 0.34 0.16
#&gt; TCGA.QR.A70O.01     7  0.3525      0.791 0.00 0.44 0.00 0.00 0.00 0.00 0.56
#&gt; TCGA.QR.A700.01     5  0.4244      1.000 0.04 0.00 0.00 0.42 0.54 0.00 0.00
#&gt; TCGA.QR.A70C.01     6  0.0504      0.645 0.00 0.02 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.WB.A80L.01     2  0.2376      0.445 0.00 0.86 0.00 0.00 0.00 0.02 0.12
#&gt; TCGA.WB.A81P.01     4  0.1363      0.615 0.04 0.00 0.00 0.94 0.02 0.00 0.00
#&gt; TCGA.RW.A68A.01     7  0.5538      0.805 0.06 0.34 0.00 0.00 0.08 0.00 0.52
#&gt; TCGA.WB.A80K.01     6  0.1006      0.637 0.00 0.02 0.00 0.00 0.00 0.96 0.02
#&gt; TCGA.QT.A5XM.01     2  0.5173      0.191 0.00 0.50 0.00 0.00 0.00 0.34 0.16
#&gt; TCGA.QR.A70X.01     2  0.1166      0.431 0.00 0.94 0.00 0.00 0.00 0.00 0.06
#&gt; TCGA.WB.A81H.01     2  0.5173      0.191 0.00 0.50 0.00 0.00 0.00 0.34 0.16
#&gt; TCGA.SR.A6MV.01     2  0.1166      0.340 0.00 0.94 0.00 0.00 0.00 0.00 0.06
#&gt; TCGA.SR.A6MP.01     4  0.5091      0.556 0.04 0.00 0.00 0.64 0.00 0.20 0.12
#&gt; TCGA.PR.A5PH.01     2  0.6016     -0.228 0.06 0.58 0.04 0.00 0.26 0.02 0.04
#&gt; TCGA.QR.A6GR.01     4  0.0000      0.639 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A686.06     6  0.1006      0.641 0.00 0.00 0.00 0.02 0.02 0.96 0.00
#&gt; TCGA.RW.A684.01     3  0.0000      0.888 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.01     6  0.6548      0.448 0.04 0.20 0.00 0.04 0.00 0.48 0.24
#&gt; TCGA.WB.A821.01     2  0.1166      0.340 0.00 0.94 0.00 0.00 0.00 0.00 0.06
#&gt; TCGA.SR.A6MZ.01     3  0.0000      0.888 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     2  0.2864      0.196 0.02 0.84 0.00 0.00 0.12 0.00 0.02
#&gt; TCGA.S7.A7WU.01     4  0.5325      0.426 0.04 0.00 0.00 0.54 0.02 0.36 0.04
#&gt; TCGA.WB.A820.01     4  0.1166      0.589 0.06 0.00 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     4  0.0000      0.639 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81Q.01     1  0.4604      0.769 0.70 0.00 0.00 0.18 0.06 0.00 0.06
#&gt; TCGA.TT.A6YJ.01     1  0.3244      0.879 0.78 0.00 0.00 0.18 0.04 0.00 0.00
#&gt; TCGA.WB.A819.01     4  0.0000      0.639 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WL.01     4  0.1363      0.571 0.04 0.00 0.00 0.94 0.02 0.00 0.00
#&gt; TCGA.WB.A817.01     6  0.5844      0.227 0.02 0.32 0.00 0.00 0.00 0.44 0.22
#&gt; TCGA.RW.A7D0.01     2  0.0000      0.386 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A80Q.01     6  0.3485      0.518 0.04 0.00 0.00 0.10 0.02 0.82 0.02
#&gt; TCGA.SR.A6MQ.01     3  0.0000      0.888 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A685.01     4  0.5460      0.491 0.04 0.00 0.00 0.58 0.00 0.24 0.14
#&gt; TCGA.SP.A6QC.01     6  0.6346      0.440 0.04 0.22 0.00 0.02 0.00 0.48 0.24
#&gt; TCGA.QR.A70G.01     4  0.0000      0.639 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81V.01     6  0.5992      0.417 0.04 0.24 0.00 0.00 0.00 0.48 0.24
#&gt; TCGA.WB.A81N.01     2  0.5421     -0.103 0.00 0.40 0.00 0.00 0.00 0.40 0.20
#&gt; TCGA.WB.A80O.01     4  0.5460      0.491 0.04 0.00 0.00 0.58 0.00 0.24 0.14
#&gt; TCGA.QT.A5XN.01     1  0.3244      0.879 0.78 0.00 0.00 0.18 0.04 0.00 0.00
#&gt; TCGA.WB.A816.01     3  0.3863      0.802 0.02 0.00 0.74 0.00 0.20 0.00 0.04
#&gt; TCGA.P7.A5NY.05     3  0.3863      0.802 0.02 0.00 0.74 0.00 0.20 0.00 0.04
#&gt; TCGA.W2.A7H5.01     3  0.0000      0.888 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     4  0.5091      0.556 0.04 0.00 0.00 0.64 0.00 0.20 0.12
#&gt; TCGA.RW.A686.01     6  0.1006      0.644 0.00 0.02 0.00 0.00 0.02 0.96 0.00
#&gt; TCGA.WB.A81I.01     5  0.4244      1.000 0.04 0.00 0.00 0.42 0.54 0.00 0.00
#&gt; TCGA.W2.A7HE.01     3  0.3863      0.802 0.02 0.00 0.74 0.00 0.20 0.00 0.04
#&gt; TCGA.QR.A702.01     5  0.4244      1.000 0.04 0.00 0.00 0.42 0.54 0.00 0.00
#&gt; TCGA.S7.A7WN.01     4  0.1166      0.589 0.06 0.00 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.SR.A6MU.01     3  0.0000      0.888 0.00 0.00 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-6-a').parent().next().next().hide();
$('#tab-node-03-get-classes-6-a').click(function(){
  $('#tab-node-03-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-7'>
<p><a id='tab-node-03-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.WB.A81K.01     2  0.5447      0.537 0.00 0.58 0.00 0.16 0.16 0.10 0.00 0.00
#&gt; TCGA.QR.A70O.01     7  0.5130      0.727 0.00 0.22 0.00 0.00 0.10 0.04 0.62 0.02
#&gt; TCGA.QR.A700.01     8  0.0471      1.000 0.00 0.00 0.00 0.02 0.00 0.00 0.00 0.98
#&gt; TCGA.QR.A70C.01     6  0.2725      0.946 0.00 0.04 0.00 0.14 0.00 0.82 0.00 0.00
#&gt; TCGA.WB.A80L.01     2  0.0471      0.561 0.00 0.98 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.WB.A81P.01     4  0.5547      0.385 0.02 0.00 0.00 0.60 0.06 0.04 0.04 0.24
#&gt; TCGA.RW.A68A.01     7  0.1341      0.716 0.00 0.08 0.00 0.00 0.00 0.00 0.92 0.00
#&gt; TCGA.WB.A80K.01     6  0.2725      0.946 0.00 0.04 0.00 0.14 0.00 0.82 0.00 0.00
#&gt; TCGA.QT.A5XM.01     2  0.5447      0.537 0.00 0.58 0.00 0.16 0.16 0.10 0.00 0.00
#&gt; TCGA.QR.A70X.01     2  0.0000      0.557 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81H.01     2  0.5447      0.537 0.00 0.58 0.00 0.16 0.16 0.10 0.00 0.00
#&gt; TCGA.SR.A6MV.01     2  0.1341      0.506 0.00 0.92 0.00 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.SR.A6MP.01     4  0.1091      0.483 0.00 0.00 0.00 0.94 0.06 0.00 0.00 0.00
#&gt; TCGA.PR.A5PH.01     2  0.5364      0.129 0.06 0.60 0.00 0.00 0.24 0.04 0.06 0.00
#&gt; TCGA.QR.A6GR.01     4  0.3015      0.432 0.00 0.00 0.00 0.68 0.00 0.00 0.00 0.32
#&gt; TCGA.RW.A686.06     6  0.3178      0.942 0.00 0.04 0.00 0.14 0.02 0.80 0.00 0.00
#&gt; TCGA.RW.A684.01     3  0.0000      0.891 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.01     4  0.6331     -0.336 0.00 0.30 0.00 0.36 0.22 0.12 0.00 0.00
#&gt; TCGA.WB.A821.01     2  0.1341      0.506 0.00 0.92 0.00 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.SR.A6MZ.01     3  0.0000      0.891 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     2  0.3293      0.292 0.00 0.74 0.00 0.00 0.22 0.00 0.04 0.00
#&gt; TCGA.S7.A7WU.01     4  0.5256      0.300 0.02 0.00 0.00 0.62 0.06 0.24 0.04 0.02
#&gt; TCGA.WB.A820.01     4  0.4106      0.401 0.02 0.00 0.00 0.64 0.04 0.00 0.00 0.30
#&gt; TCGA.WB.A81F.01     4  0.3015      0.432 0.00 0.00 0.00 0.68 0.00 0.00 0.00 0.32
#&gt; TCGA.WB.A81Q.01     1  0.2807      0.542 0.86 0.00 0.00 0.06 0.00 0.02 0.04 0.02
#&gt; TCGA.TT.A6YJ.01     1  0.5080      0.779 0.54 0.00 0.00 0.04 0.32 0.00 0.00 0.10
#&gt; TCGA.WB.A819.01     4  0.3015      0.432 0.00 0.00 0.00 0.68 0.00 0.00 0.00 0.32
#&gt; TCGA.S7.A7WL.01     4  0.5547      0.327 0.04 0.00 0.00 0.54 0.08 0.00 0.04 0.30
#&gt; TCGA.WB.A817.01     2  0.6225      0.357 0.00 0.42 0.00 0.24 0.22 0.12 0.00 0.00
#&gt; TCGA.RW.A7D0.01     2  0.0808      0.538 0.00 0.96 0.00 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.WB.A80Q.01     6  0.2114      0.821 0.00 0.00 0.00 0.16 0.00 0.84 0.00 0.00
#&gt; TCGA.SR.A6MQ.01     3  0.0000      0.891 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A685.01     4  0.1341      0.478 0.00 0.00 0.00 0.92 0.08 0.00 0.00 0.00
#&gt; TCGA.SP.A6QC.01     4  0.6331     -0.336 0.00 0.30 0.00 0.36 0.22 0.12 0.00 0.00
#&gt; TCGA.QR.A70G.01     4  0.3015      0.432 0.00 0.00 0.00 0.68 0.00 0.00 0.00 0.32
#&gt; TCGA.WB.A81V.01     4  0.6331     -0.336 0.00 0.30 0.00 0.36 0.22 0.12 0.00 0.00
#&gt; TCGA.WB.A81N.01     2  0.6014      0.435 0.00 0.48 0.00 0.20 0.20 0.12 0.00 0.00
#&gt; TCGA.WB.A80O.01     4  0.1341      0.478 0.00 0.00 0.00 0.92 0.08 0.00 0.00 0.00
#&gt; TCGA.QT.A5XN.01     1  0.5660      0.779 0.54 0.00 0.00 0.04 0.28 0.04 0.00 0.10
#&gt; TCGA.WB.A816.01     3  0.2650      0.807 0.00 0.00 0.76 0.00 0.24 0.00 0.00 0.00
#&gt; TCGA.P7.A5NY.05     3  0.2756      0.791 0.00 0.00 0.74 0.00 0.26 0.00 0.00 0.00
#&gt; TCGA.W2.A7H5.01     3  0.0000      0.891 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     4  0.1091      0.483 0.00 0.00 0.00 0.94 0.06 0.00 0.00 0.00
#&gt; TCGA.RW.A686.01     6  0.3178      0.942 0.00 0.04 0.00 0.14 0.02 0.80 0.00 0.00
#&gt; TCGA.WB.A81I.01     8  0.0471      1.000 0.00 0.00 0.00 0.02 0.00 0.00 0.00 0.98
#&gt; TCGA.W2.A7HE.01     3  0.2650      0.807 0.00 0.00 0.76 0.00 0.24 0.00 0.00 0.00
#&gt; TCGA.QR.A702.01     8  0.0471      1.000 0.00 0.00 0.00 0.02 0.00 0.00 0.00 0.98
#&gt; TCGA.S7.A7WN.01     4  0.4106      0.401 0.02 0.00 0.00 0.64 0.04 0.00 0.00 0.30
#&gt; TCGA.SR.A6MU.01     3  0.0000      0.891 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-7-a').parent().next().next().hide();
$('#tab-node-03-get-classes-7-a').click(function(){
  $('#tab-node-03-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-03-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-03-consensus-heatmap'>
<ul>
<li><a href='#tab-node-03-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-03-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-03-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-03-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-03-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-03-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-03-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-03-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-03-membership-heatmap'>
<ul>
<li><a href='#tab-node-03-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-03-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-03-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-03-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-03-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-03-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-03-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-1-1.png" alt="plot of chunk tab-node-03-membership-heatmap-1"/></p>

</div>
<div id='tab-node-03-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-2-1.png" alt="plot of chunk tab-node-03-membership-heatmap-2"/></p>

</div>
<div id='tab-node-03-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-3-1.png" alt="plot of chunk tab-node-03-membership-heatmap-3"/></p>

</div>
<div id='tab-node-03-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-4-1.png" alt="plot of chunk tab-node-03-membership-heatmap-4"/></p>

</div>
<div id='tab-node-03-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-5-1.png" alt="plot of chunk tab-node-03-membership-heatmap-5"/></p>

</div>
<div id='tab-node-03-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-6-1.png" alt="plot of chunk tab-node-03-membership-heatmap-6"/></p>

</div>
<div id='tab-node-03-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-7-1.png" alt="plot of chunk tab-node-03-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-03-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-03-get-signatures'>
<ul>
<li><a href='#tab-node-03-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-03-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-03-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-03-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-03-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-03-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-03-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-1-1.png" alt="plot of chunk tab-node-03-get-signatures-1"/></p>

</div>
<div id='tab-node-03-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-2-1.png" alt="plot of chunk tab-node-03-get-signatures-2"/></p>

</div>
<div id='tab-node-03-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-3-1.png" alt="plot of chunk tab-node-03-get-signatures-3"/></p>

</div>
<div id='tab-node-03-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-4-1.png" alt="plot of chunk tab-node-03-get-signatures-4"/></p>

</div>
<div id='tab-node-03-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-5-1.png" alt="plot of chunk tab-node-03-get-signatures-5"/></p>

</div>
<div id='tab-node-03-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-6-1.png" alt="plot of chunk tab-node-03-get-signatures-6"/></p>

</div>
<div id='tab-node-03-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-7-1.png" alt="plot of chunk tab-node-03-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-03-signature_compare](figure_cola/node-03-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-03-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-03-dimension-reduction'>
<ul>
<li><a href='#tab-node-03-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-03-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-03-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-03-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-03-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-03-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-03-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-1-1.png" alt="plot of chunk tab-node-03-dimension-reduction-1"/></p>

</div>
<div id='tab-node-03-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-2-1.png" alt="plot of chunk tab-node-03-dimension-reduction-2"/></p>

</div>
<div id='tab-node-03-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-3-1.png" alt="plot of chunk tab-node-03-dimension-reduction-3"/></p>

</div>
<div id='tab-node-03-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-4-1.png" alt="plot of chunk tab-node-03-dimension-reduction-4"/></p>

</div>
<div id='tab-node-03-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-5-1.png" alt="plot of chunk tab-node-03-dimension-reduction-5"/></p>

</div>
<div id='tab-node-03-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-6-1.png" alt="plot of chunk tab-node-03-dimension-reduction-6"/></p>

</div>
<div id='tab-node-03-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-7-1.png" alt="plot of chunk tab-node-03-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-03-collect-classes](figure_cola/node-03-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node031


Parent node: [Node03](#Node03).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0311-leaf
        ,
                Node0312-leaf
        ,
                Node0313-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0411-leaf
        ,
                Node0412-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["031"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 20 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 8.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-031-collect-plots](figure_cola/node-031-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-031-select-partition-number](figure_cola/node-031-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           0.996       0.998         0.5217 0.479   0.479
#> 3 3 1.000           0.998       0.999         0.3016 0.842   0.670
#> 4 4 0.853           0.881       0.956         0.0625 0.979   0.934
#> 5 5 0.805           0.821       0.889         0.0917 0.895   0.649
#> 6 6 0.821           0.828       0.924         0.0599 0.958   0.784
#> 7 7 0.895           0.812       0.921         0.0340 0.984   0.897
#> 8 8 0.947           0.786       0.935         0.0227 0.979   0.846
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 8
#> attr(,"optional")
#> [1] 2 3
```

There is also optional best $k$ = 2 3 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-031-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-031-get-classes'>
<ul>
<li><a href='#tab-node-031-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-031-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-031-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-031-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-031-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-031-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-031-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-031-get-classes-1'>
<p><a id='tab-node-031-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.QR.A700.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A81P.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.SR.A6MP.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.QR.A6GR.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.S7.A7WU.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.WB.A820.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A81F.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A81Q.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.TT.A6YJ.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.WB.A819.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.S7.A7WL.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A80Q.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.RW.A685.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.QR.A70G.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A80O.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.QT.A5XN.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.RX.A8JQ.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.WB.A81I.01     2   0.242      0.958 0.04 0.96
#&gt; TCGA.QR.A702.01     2   0.000      0.996 0.00 1.00
#&gt; TCGA.S7.A7WN.01     1   0.000      1.000 1.00 0.00
</code></pre>

<script>
$('#tab-node-031-get-classes-1-a').parent().next().next().hide();
$('#tab-node-031-get-classes-1-a').click(function(){
  $('#tab-node-031-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-031-get-classes-2'>
<p><a id='tab-node-031-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1   p2   p3
#&gt; TCGA.QR.A700.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A81P.01     3  0.0000      0.995  0 0.00 1.00
#&gt; TCGA.SR.A6MP.01     2  0.0000      1.000  0 1.00 0.00
#&gt; TCGA.QR.A6GR.01     2  0.0000      1.000  0 1.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.0000      0.995  0 0.00 1.00
#&gt; TCGA.WB.A820.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A81F.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A81Q.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     2  0.0000      1.000  0 1.00 0.00
#&gt; TCGA.WB.A819.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.S7.A7WL.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A80Q.01     3  0.0892      0.980  0 0.02 0.98
#&gt; TCGA.RW.A685.01     2  0.0000      1.000  0 1.00 0.00
#&gt; TCGA.QR.A70G.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A80O.01     2  0.0000      1.000  0 1.00 0.00
#&gt; TCGA.QT.A5XN.01     2  0.0000      1.000  0 1.00 0.00
#&gt; TCGA.RX.A8JQ.01     1  0.0000      1.000  1 0.00 0.00
#&gt; TCGA.WB.A81I.01     3  0.0000      0.995  0 0.00 1.00
#&gt; TCGA.QR.A702.01     3  0.0000      0.995  0 0.00 1.00
#&gt; TCGA.S7.A7WN.01     1  0.0000      1.000  1 0.00 0.00
</code></pre>

<script>
$('#tab-node-031-get-classes-2-a').parent().next().next().hide();
$('#tab-node-031-get-classes-2-a').click(function(){
  $('#tab-node-031-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-031-get-classes-3'>
<p><a id='tab-node-031-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1 p2   p3   p4
#&gt; TCGA.QR.A700.01     1   0.000      0.909 1.00  0 0.00 0.00
#&gt; TCGA.WB.A81P.01     3   0.000      1.000 0.00  0 1.00 0.00
#&gt; TCGA.SR.A6MP.01     2   0.000      1.000 0.00  1 0.00 0.00
#&gt; TCGA.QR.A6GR.01     2   0.000      1.000 0.00  1 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3   0.000      1.000 0.00  0 1.00 0.00
#&gt; TCGA.WB.A820.01     1   0.000      0.909 1.00  0 0.00 0.00
#&gt; TCGA.WB.A81F.01     1   0.234      0.886 0.90  0 0.00 0.10
#&gt; TCGA.WB.A81Q.01     1   0.000      0.909 1.00  0 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     2   0.000      1.000 0.00  1 0.00 0.00
#&gt; TCGA.WB.A819.01     1   0.265      0.875 0.88  0 0.00 0.12
#&gt; TCGA.S7.A7WL.01     1   0.234      0.886 0.90  0 0.00 0.10
#&gt; TCGA.WB.A80Q.01     3   0.000      1.000 0.00  0 1.00 0.00
#&gt; TCGA.RW.A685.01     2   0.000      1.000 0.00  1 0.00 0.00
#&gt; TCGA.QR.A70G.01     1   0.495      0.424 0.56  0 0.00 0.44
#&gt; TCGA.WB.A80O.01     2   0.000      1.000 0.00  1 0.00 0.00
#&gt; TCGA.QT.A5XN.01     2   0.000      1.000 0.00  1 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     1   0.000      0.909 1.00  0 0.00 0.00
#&gt; TCGA.WB.A81I.01     4   0.265      0.000 0.00  0 0.12 0.88
#&gt; TCGA.QR.A702.01     3   0.000      1.000 0.00  0 1.00 0.00
#&gt; TCGA.S7.A7WN.01     1   0.000      0.909 1.00  0 0.00 0.00
</code></pre>

<script>
$('#tab-node-031-get-classes-3-a').parent().next().next().hide();
$('#tab-node-031-get-classes-3-a').click(function(){
  $('#tab-node-031-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-031-get-classes-4'>
<p><a id='tab-node-031-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2  p3   p4   p5
#&gt; TCGA.QR.A700.01     1  0.1043      0.936 0.96 0.00 0.0 0.00 0.04
#&gt; TCGA.WB.A81P.01     3  0.0000      0.963 0.00 0.00 1.0 0.00 0.00
#&gt; TCGA.SR.A6MP.01     2  0.0000      0.887 0.00 1.00 0.0 0.00 0.00
#&gt; TCGA.QR.A6GR.01     2  0.0000      0.887 0.00 1.00 0.0 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.0000      0.963 0.00 0.00 1.0 0.00 0.00
#&gt; TCGA.WB.A820.01     1  0.0000      0.984 1.00 0.00 0.0 0.00 0.00
#&gt; TCGA.WB.A81F.01     5  0.4302      0.651 0.48 0.00 0.0 0.00 0.52
#&gt; TCGA.WB.A81Q.01     1  0.0000      0.984 1.00 0.00 0.0 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     2  0.4676      0.771 0.00 0.74 0.0 0.14 0.12
#&gt; TCGA.WB.A819.01     5  0.3796      0.754 0.30 0.00 0.0 0.00 0.70
#&gt; TCGA.S7.A7WL.01     5  0.4262      0.718 0.44 0.00 0.0 0.00 0.56
#&gt; TCGA.WB.A80Q.01     3  0.2610      0.884 0.00 0.06 0.9 0.02 0.02
#&gt; TCGA.RW.A685.01     2  0.0609      0.884 0.00 0.98 0.0 0.02 0.00
#&gt; TCGA.QR.A70G.01     5  0.2516      0.576 0.14 0.00 0.0 0.00 0.86
#&gt; TCGA.WB.A80O.01     2  0.0609      0.884 0.00 0.98 0.0 0.02 0.00
#&gt; TCGA.QT.A5XN.01     2  0.4676      0.771 0.00 0.74 0.0 0.14 0.12
#&gt; TCGA.RX.A8JQ.01     1  0.0000      0.984 1.00 0.00 0.0 0.00 0.00
#&gt; TCGA.WB.A81I.01     4  0.2732      0.000 0.00 0.00 0.0 0.84 0.16
#&gt; TCGA.QR.A702.01     3  0.0000      0.963 0.00 0.00 1.0 0.00 0.00
#&gt; TCGA.S7.A7WN.01     1  0.0000      0.984 1.00 0.00 0.0 0.00 0.00
</code></pre>

<script>
$('#tab-node-031-get-classes-4-a').parent().next().next().hide();
$('#tab-node-031-get-classes-4-a').click(function(){
  $('#tab-node-031-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-031-get-classes-5'>
<p><a id='tab-node-031-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.QR.A700.01     1  0.2190      0.896 0.90 0.00 0.00 0.00 0.04 0.06
#&gt; TCGA.WB.A81P.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MP.01     2  0.0937      0.947 0.00 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.QR.A6GR.01     2  0.0000      0.983 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WB.A820.01     1  0.0000      0.976 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     5  0.4348      0.604 0.32 0.00 0.00 0.00 0.64 0.04
#&gt; TCGA.WB.A81Q.01     1  0.0000      0.976 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     6  0.2793      1.000 0.00 0.20 0.00 0.00 0.00 0.80
#&gt; TCGA.WB.A819.01     5  0.0000      0.724 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7WL.01     5  0.3679      0.719 0.20 0.00 0.00 0.00 0.76 0.04
#&gt; TCGA.WB.A80Q.01     3  0.4834      0.528 0.00 0.26 0.64 0.00 0.00 0.10
#&gt; TCGA.RW.A685.01     2  0.0000      0.983 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70G.01     5  0.0547      0.714 0.00 0.00 0.00 0.02 0.98 0.00
#&gt; TCGA.WB.A80O.01     2  0.0000      0.983 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XN.01     6  0.2793      1.000 0.00 0.20 0.00 0.00 0.00 0.80
#&gt; TCGA.RX.A8JQ.01     1  0.0000      0.976 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81I.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A702.01     3  0.0000      0.860 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WN.01     1  0.0000      0.976 1.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-031-get-classes-5-a').parent().next().next().hide();
$('#tab-node-031-get-classes-5-a').click(function(){
  $('#tab-node-031-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-031-get-classes-6'>
<p><a id='tab-node-031-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.QR.A700.01     1  0.4378      0.657 0.70 0.00 0.00 0.00 0.08 0.02 0.20
#&gt; TCGA.WB.A81P.01     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MP.01     2  0.1433      0.909 0.00 0.92 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.QR.A6GR.01     2  0.0000      0.965 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A820.01     1  0.0000      0.921 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     5  0.4308      0.757 0.10 0.00 0.00 0.00 0.72 0.02 0.16
#&gt; TCGA.WB.A81Q.01     1  0.0000      0.921 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     6  0.1433      1.000 0.00 0.08 0.00 0.00 0.00 0.92 0.00
#&gt; TCGA.WB.A819.01     5  0.0000      0.801 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7WL.01     5  0.3722      0.788 0.02 0.00 0.00 0.00 0.76 0.04 0.18
#&gt; TCGA.WB.A80Q.01     7  0.4328      0.000 0.00 0.06 0.34 0.00 0.00 0.00 0.60
#&gt; TCGA.RW.A685.01     2  0.0000      0.965 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70G.01     5  0.1860      0.763 0.00 0.00 0.00 0.04 0.92 0.02 0.02
#&gt; TCGA.WB.A80O.01     2  0.0504      0.960 0.00 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.QT.A5XN.01     6  0.1433      1.000 0.00 0.08 0.00 0.00 0.00 0.92 0.00
#&gt; TCGA.RX.A8JQ.01     1  0.0504      0.910 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.WB.A81I.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A702.01     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WN.01     1  0.0000      0.921 1.00 0.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-031-get-classes-6-a').parent().next().next().hide();
$('#tab-node-031-get-classes-6-a').click(function(){
  $('#tab-node-031-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-031-get-classes-7'>
<p><a id='tab-node-031-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3 p4   p5   p6   p7   p8
#&gt; TCGA.QR.A700.01     8  0.2938      0.000 0.30 0.00 0.00  0 0.00 0.00 0.00 0.70
#&gt; TCGA.WB.A81P.01     3  0.0000      0.989 0.00 0.00 1.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.SR.A6MP.01     2  0.1275      0.948 0.00 0.94 0.00  0 0.00 0.04 0.00 0.02
#&gt; TCGA.QR.A6GR.01     2  0.0471      0.970 0.00 0.98 0.00  0 0.00 0.02 0.00 0.00
#&gt; TCGA.S7.A7WU.01     3  0.0000      0.989 0.00 0.00 1.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A820.01     1  0.0000      0.990 1.00 0.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.WB.A81F.01     5  0.1341      0.749 0.08 0.00 0.00  0 0.92 0.00 0.00 0.00
#&gt; TCGA.WB.A81Q.01     1  0.0000      0.990 1.00 0.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YJ.01     6  0.0471      1.000 0.00 0.02 0.00  0 0.00 0.98 0.00 0.00
#&gt; TCGA.WB.A819.01     5  0.2859      0.776 0.00 0.00 0.00  0 0.82 0.02 0.02 0.14
#&gt; TCGA.S7.A7WL.01     5  0.2623      0.703 0.00 0.00 0.00  0 0.84 0.00 0.06 0.10
#&gt; TCGA.WB.A80Q.01     7  0.2132      0.000 0.00 0.04 0.08  0 0.00 0.00 0.88 0.00
#&gt; TCGA.RW.A685.01     2  0.0000      0.973 0.00 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70G.01     5  0.3843      0.720 0.00 0.00 0.00  0 0.70 0.02 0.04 0.24
#&gt; TCGA.WB.A80O.01     2  0.0000      0.973 0.00 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.QT.A5XN.01     6  0.0471      1.000 0.00 0.02 0.00  0 0.00 0.98 0.00 0.00
#&gt; TCGA.RX.A8JQ.01     1  0.0471      0.971 0.98 0.00 0.00  0 0.00 0.00 0.00 0.02
#&gt; TCGA.WB.A81I.01     4  0.0000      0.000 0.00 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A702.01     3  0.0471      0.978 0.00 0.00 0.98  0 0.00 0.00 0.02 0.00
#&gt; TCGA.S7.A7WN.01     1  0.0000      0.990 1.00 0.00 0.00  0 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-031-get-classes-7-a').parent().next().next().hide();
$('#tab-node-031-get-classes-7-a').click(function(){
  $('#tab-node-031-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-031-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-031-consensus-heatmap'>
<ul>
<li><a href='#tab-node-031-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-031-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-031-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-031-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-031-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-031-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-031-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-031-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-031-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-031-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-031-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-031-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-031-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-031-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-031-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-031-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-031-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-031-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-031-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-031-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-031-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-031-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-031-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-031-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-031-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-031-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-031-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-031-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-031-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-031-membership-heatmap'>
<ul>
<li><a href='#tab-node-031-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-031-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-031-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-031-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-031-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-031-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-031-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-031-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-031-membership-heatmap-1-1.png" alt="plot of chunk tab-node-031-membership-heatmap-1"/></p>

</div>
<div id='tab-node-031-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-031-membership-heatmap-2-1.png" alt="plot of chunk tab-node-031-membership-heatmap-2"/></p>

</div>
<div id='tab-node-031-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-031-membership-heatmap-3-1.png" alt="plot of chunk tab-node-031-membership-heatmap-3"/></p>

</div>
<div id='tab-node-031-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-031-membership-heatmap-4-1.png" alt="plot of chunk tab-node-031-membership-heatmap-4"/></p>

</div>
<div id='tab-node-031-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-031-membership-heatmap-5-1.png" alt="plot of chunk tab-node-031-membership-heatmap-5"/></p>

</div>
<div id='tab-node-031-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-031-membership-heatmap-6-1.png" alt="plot of chunk tab-node-031-membership-heatmap-6"/></p>

</div>
<div id='tab-node-031-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-031-membership-heatmap-7-1.png" alt="plot of chunk tab-node-031-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-031-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-031-get-signatures'>
<ul>
<li><a href='#tab-node-031-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-031-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-031-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-031-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-031-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-031-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-031-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-031-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-031-get-signatures-1-1.png" alt="plot of chunk tab-node-031-get-signatures-1"/></p>

</div>
<div id='tab-node-031-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-031-get-signatures-2-1.png" alt="plot of chunk tab-node-031-get-signatures-2"/></p>

</div>
<div id='tab-node-031-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-031-get-signatures-3-1.png" alt="plot of chunk tab-node-031-get-signatures-3"/></p>

</div>
<div id='tab-node-031-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-031-get-signatures-4-1.png" alt="plot of chunk tab-node-031-get-signatures-4"/></p>

</div>
<div id='tab-node-031-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-031-get-signatures-5-1.png" alt="plot of chunk tab-node-031-get-signatures-5"/></p>

</div>
<div id='tab-node-031-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-031-get-signatures-6-1.png" alt="plot of chunk tab-node-031-get-signatures-6"/></p>

</div>
<div id='tab-node-031-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-031-get-signatures-7-1.png" alt="plot of chunk tab-node-031-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-031-signature_compare](figure_cola/node-031-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-031-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-031-dimension-reduction'>
<ul>
<li><a href='#tab-node-031-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-031-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-031-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-031-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-031-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-031-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-031-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-031-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-031-dimension-reduction-1-1.png" alt="plot of chunk tab-node-031-dimension-reduction-1"/></p>

</div>
<div id='tab-node-031-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-031-dimension-reduction-2-1.png" alt="plot of chunk tab-node-031-dimension-reduction-2"/></p>

</div>
<div id='tab-node-031-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-031-dimension-reduction-3-1.png" alt="plot of chunk tab-node-031-dimension-reduction-3"/></p>

</div>
<div id='tab-node-031-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-031-dimension-reduction-4-1.png" alt="plot of chunk tab-node-031-dimension-reduction-4"/></p>

</div>
<div id='tab-node-031-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-031-dimension-reduction-5-1.png" alt="plot of chunk tab-node-031-dimension-reduction-5"/></p>

</div>
<div id='tab-node-031-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-031-dimension-reduction-6-1.png" alt="plot of chunk tab-node-031-dimension-reduction-6"/></p>

</div>
<div id='tab-node-031-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-031-dimension-reduction-7-1.png" alt="plot of chunk tab-node-031-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-031-collect-classes](figure_cola/node-031-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node032


Parent node: [Node03](#Node03).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0311-leaf
        ,
                Node0312-leaf
        ,
                Node0313-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0411-leaf
        ,
                Node0412-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["032"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 21 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 6.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-032-collect-plots](figure_cola/node-032-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-032-select-partition-number](figure_cola/node-032-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5243 0.476   0.476
#> 3 3 1.000           1.000       1.000         0.2722 0.743   0.518
#> 4 4 0.863           0.944       0.950         0.0895 0.943   0.829
#> 5 5 0.905           0.800       0.917         0.0975 0.905   0.655
#> 6 6 0.910           0.805       0.929         0.0356 0.957   0.786
#> 7 7 0.924           0.802       0.953         0.0172 0.981   0.892
#> 8 8 0.900           0.755       0.913         0.0282 0.981   0.879
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 6
#> attr(,"optional")
#> [1] 2 3 5
```

There is also optional best $k$ = 2 3 5 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-032-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-032-get-classes'>
<ul>
<li><a href='#tab-node-032-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-032-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-032-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-032-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-032-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-032-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-032-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-032-get-classes-1'>
<p><a id='tab-node-032-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.WB.A81K.01     1       0          1  1  0
#&gt; TCGA.QR.A70O.01     2       0          1  0  1
#&gt; TCGA.QR.A70C.01     2       0          1  0  1
#&gt; TCGA.WB.A80L.01     2       0          1  0  1
#&gt; TCGA.RW.A68A.01     2       0          1  0  1
#&gt; TCGA.WB.A80K.01     1       0          1  1  0
#&gt; TCGA.QT.A5XM.01     1       0          1  1  0
#&gt; TCGA.QR.A70X.01     2       0          1  0  1
#&gt; TCGA.WB.A81H.01     2       0          1  0  1
#&gt; TCGA.SR.A6MV.01     2       0          1  0  1
#&gt; TCGA.PR.A5PH.01     1       0          1  1  0
#&gt; TCGA.RW.A686.06     1       0          1  1  0
#&gt; TCGA.SQ.A6I4.01     1       0          1  1  0
#&gt; TCGA.WB.A821.01     2       0          1  0  1
#&gt; TCGA.SP.A6QK.01     2       0          1  0  1
#&gt; TCGA.WB.A817.01     1       0          1  1  0
#&gt; TCGA.RW.A7D0.01     2       0          1  0  1
#&gt; TCGA.SP.A6QC.01     1       0          1  1  0
#&gt; TCGA.WB.A81V.01     1       0          1  1  0
#&gt; TCGA.WB.A81N.01     2       0          1  0  1
#&gt; TCGA.RW.A686.01     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-032-get-classes-1-a').parent().next().next().hide();
$('#tab-node-032-get-classes-1-a').click(function(){
  $('#tab-node-032-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-2'>
<p><a id='tab-node-032-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2 p3
#&gt; TCGA.WB.A81K.01     1       0          1  1  0  0
#&gt; TCGA.QR.A70O.01     2       0          1  0  1  0
#&gt; TCGA.QR.A70C.01     2       0          1  0  1  0
#&gt; TCGA.WB.A80L.01     1       0          1  1  0  0
#&gt; TCGA.RW.A68A.01     1       0          1  1  0  0
#&gt; TCGA.WB.A80K.01     3       0          1  0  0  1
#&gt; TCGA.QT.A5XM.01     1       0          1  1  0  0
#&gt; TCGA.QR.A70X.01     2       0          1  0  1  0
#&gt; TCGA.WB.A81H.01     2       0          1  0  1  0
#&gt; TCGA.SR.A6MV.01     2       0          1  0  1  0
#&gt; TCGA.PR.A5PH.01     3       0          1  0  0  1
#&gt; TCGA.RW.A686.06     3       0          1  0  0  1
#&gt; TCGA.SQ.A6I4.01     1       0          1  1  0  0
#&gt; TCGA.WB.A821.01     2       0          1  0  1  0
#&gt; TCGA.SP.A6QK.01     2       0          1  0  1  0
#&gt; TCGA.WB.A817.01     1       0          1  1  0  0
#&gt; TCGA.RW.A7D0.01     2       0          1  0  1  0
#&gt; TCGA.SP.A6QC.01     1       0          1  1  0  0
#&gt; TCGA.WB.A81V.01     1       0          1  1  0  0
#&gt; TCGA.WB.A81N.01     2       0          1  0  1  0
#&gt; TCGA.RW.A686.01     3       0          1  0  0  1
</code></pre>

<script>
$('#tab-node-032-get-classes-2-a').parent().next().next().hide();
$('#tab-node-032-get-classes-2-a').click(function(){
  $('#tab-node-032-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-3'>
<p><a id='tab-node-032-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4
#&gt; TCGA.WB.A81K.01     1  0.0000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.QR.A70O.01     2  0.2921      0.910 0.00 0.86  0 0.14
#&gt; TCGA.QR.A70C.01     2  0.0707      0.921 0.00 0.98  0 0.02
#&gt; TCGA.WB.A80L.01     4  0.4406      0.771 0.30 0.00  0 0.70
#&gt; TCGA.RW.A68A.01     4  0.2921      0.807 0.14 0.00  0 0.86
#&gt; TCGA.WB.A80K.01     3  0.0000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.QT.A5XM.01     1  0.0000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.QR.A70X.01     2  0.0707      0.921 0.00 0.98  0 0.02
#&gt; TCGA.WB.A81H.01     2  0.0707      0.921 0.00 0.98  0 0.02
#&gt; TCGA.SR.A6MV.01     2  0.2921      0.910 0.00 0.86  0 0.14
#&gt; TCGA.PR.A5PH.01     3  0.0000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.RW.A686.06     3  0.0000      1.000 0.00 0.00  1 0.00
#&gt; TCGA.SQ.A6I4.01     1  0.0000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.WB.A821.01     2  0.2921      0.910 0.00 0.86  0 0.14
#&gt; TCGA.SP.A6QK.01     2  0.0000      0.925 0.00 1.00  0 0.00
#&gt; TCGA.WB.A817.01     1  0.0000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.RW.A7D0.01     2  0.0000      0.925 0.00 1.00  0 0.00
#&gt; TCGA.SP.A6QC.01     1  0.0000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.WB.A81V.01     1  0.0000      1.000 1.00 0.00  0 0.00
#&gt; TCGA.WB.A81N.01     2  0.2921      0.910 0.00 0.86  0 0.14
#&gt; TCGA.RW.A686.01     3  0.0000      1.000 0.00 0.00  1 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-3-a').parent().next().next().hide();
$('#tab-node-032-get-classes-3-a').click(function(){
  $('#tab-node-032-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-4'>
<p><a id='tab-node-032-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5
#&gt; TCGA.WB.A81K.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.QR.A70O.01     2   0.000      0.811 0.00 1.00  0 0.00 0.00
#&gt; TCGA.QR.A70C.01     5   0.000      0.467 0.00 0.00  0 0.00 1.00
#&gt; TCGA.WB.A80L.01     4   0.342      0.865 0.08 0.00  0 0.84 0.08
#&gt; TCGA.RW.A68A.01     4   0.000      0.867 0.00 0.00  0 1.00 0.00
#&gt; TCGA.WB.A80K.01     3   0.000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.QT.A5XM.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.QR.A70X.01     5   0.389      0.713 0.00 0.32  0 0.00 0.68
#&gt; TCGA.WB.A81H.01     5   0.389      0.713 0.00 0.32  0 0.00 0.68
#&gt; TCGA.SR.A6MV.01     2   0.000      0.811 0.00 1.00  0 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3   0.000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.RW.A686.06     3   0.000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.SQ.A6I4.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.WB.A821.01     2   0.000      0.811 0.00 1.00  0 0.00 0.00
#&gt; TCGA.SP.A6QK.01     5   0.429      0.466 0.00 0.46  0 0.00 0.54
#&gt; TCGA.WB.A817.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.RW.A7D0.01     2   0.430     -0.536 0.00 0.52  0 0.00 0.48
#&gt; TCGA.SP.A6QC.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.WB.A81V.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.WB.A81N.01     2   0.000      0.811 0.00 1.00  0 0.00 0.00
#&gt; TCGA.RW.A686.01     3   0.000      1.000 0.00 0.00  1 0.00 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-4-a').parent().next().next().hide();
$('#tab-node-032-get-classes-4-a').click(function(){
  $('#tab-node-032-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-5'>
<p><a id='tab-node-032-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6
#&gt; TCGA.WB.A81K.01     1  0.0547      0.988 0.98 0.00  0 0.02 0.00 0.00
#&gt; TCGA.QR.A70O.01     2  0.0000      0.967 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.QR.A70C.01     5  0.4534      0.298 0.00 0.00  0 0.04 0.58 0.38
#&gt; TCGA.WB.A80L.01     4  0.0000      0.000 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.RW.A68A.01     6  0.3706      0.000 0.00 0.00  0 0.38 0.00 0.62
#&gt; TCGA.WB.A80K.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.QT.A5XM.01     1  0.0000      0.988 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.QR.A70X.01     5  0.0937      0.742 0.00 0.04  0 0.00 0.96 0.00
#&gt; TCGA.WB.A81H.01     5  0.0937      0.742 0.00 0.04  0 0.00 0.96 0.00
#&gt; TCGA.SR.A6MV.01     2  0.0000      0.967 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.RW.A686.06     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.SQ.A6I4.01     1  0.0000      0.988 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.WB.A821.01     2  0.0000      0.967 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.SP.A6QK.01     5  0.3076      0.699 0.00 0.24  0 0.00 0.76 0.00
#&gt; TCGA.WB.A817.01     1  0.0547      0.988 0.98 0.00  0 0.02 0.00 0.00
#&gt; TCGA.RW.A7D0.01     5  0.3076      0.699 0.00 0.24  0 0.00 0.76 0.00
#&gt; TCGA.SP.A6QC.01     1  0.0000      0.988 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.WB.A81V.01     1  0.0547      0.988 0.98 0.00  0 0.02 0.00 0.00
#&gt; TCGA.WB.A81N.01     2  0.1556      0.895 0.00 0.92  0 0.00 0.08 0.00
#&gt; TCGA.RW.A686.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-5-a').parent().next().next().hide();
$('#tab-node-032-get-classes-5-a').click(function(){
  $('#tab-node-032-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-6'>
<p><a id='tab-node-032-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1   p2   p3   p4   p5   p6  p7
#&gt; TCGA.WB.A81K.01     1   0.000      1.000  1 0.00 0.00 0.00 0.00 0.00 0.0
#&gt; TCGA.QR.A70O.01     2   0.000      0.877  0 1.00 0.00 0.00 0.00 0.00 0.0
#&gt; TCGA.QR.A70C.01     7   0.167      0.000  0 0.00 0.00 0.00 0.10 0.00 0.9
#&gt; TCGA.WB.A80L.01     4   0.143      0.000  0 0.00 0.00 0.92 0.00 0.08 0.0
#&gt; TCGA.RW.A68A.01     6   0.000      0.000  0 0.00 0.00 0.00 0.00 1.00 0.0
#&gt; TCGA.WB.A80K.01     3   0.306      0.885  0 0.00 0.82 0.08 0.00 0.00 0.1
#&gt; TCGA.QT.A5XM.01     1   0.000      1.000  1 0.00 0.00 0.00 0.00 0.00 0.0
#&gt; TCGA.QR.A70X.01     5   0.000      0.933  0 0.00 0.00 0.00 1.00 0.00 0.0
#&gt; TCGA.WB.A81H.01     5   0.000      0.933  0 0.00 0.00 0.00 1.00 0.00 0.0
#&gt; TCGA.SR.A6MV.01     2   0.117      0.923  0 0.94 0.00 0.00 0.06 0.00 0.0
#&gt; TCGA.PR.A5PH.01     3   0.306      0.885  0 0.00 0.82 0.08 0.00 0.00 0.1
#&gt; TCGA.RW.A686.06     3   0.000      0.885  0 0.00 1.00 0.00 0.00 0.00 0.0
#&gt; TCGA.SQ.A6I4.01     1   0.000      1.000  1 0.00 0.00 0.00 0.00 0.00 0.0
#&gt; TCGA.WB.A821.01     2   0.143      0.923  0 0.92 0.00 0.00 0.08 0.00 0.0
#&gt; TCGA.SP.A6QK.01     5   0.117      0.932  0 0.06 0.00 0.00 0.94 0.00 0.0
#&gt; TCGA.WB.A817.01     1   0.000      1.000  1 0.00 0.00 0.00 0.00 0.00 0.0
#&gt; TCGA.RW.A7D0.01     5   0.143      0.918  0 0.08 0.00 0.00 0.92 0.00 0.0
#&gt; TCGA.SP.A6QC.01     1   0.000      1.000  1 0.00 0.00 0.00 0.00 0.00 0.0
#&gt; TCGA.WB.A81V.01     1   0.000      1.000  1 0.00 0.00 0.00 0.00 0.00 0.0
#&gt; TCGA.WB.A81N.01     2   0.226      0.859  0 0.84 0.00 0.00 0.16 0.00 0.0
#&gt; TCGA.RW.A686.01     3   0.000      0.885  0 0.00 1.00 0.00 0.00 0.00 0.0
</code></pre>

<script>
$('#tab-node-032-get-classes-6-a').parent().next().next().hide();
$('#tab-node-032-get-classes-6-a').click(function(){
  $('#tab-node-032-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-7'>
<p><a id='tab-node-032-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3 p4   p5 p6   p7   p8
#&gt; TCGA.WB.A81K.01     1  0.3303      0.850 0.76 0.02 0.00  0 0.00  0 0.02 0.20
#&gt; TCGA.QR.A70O.01     2  0.0941      0.884 0.00 0.96 0.00  0 0.02  0 0.00 0.02
#&gt; TCGA.QR.A70C.01     7  0.0471      0.000 0.00 0.00 0.00  0 0.02  0 0.98 0.00
#&gt; TCGA.WB.A80L.01     4  0.0000      0.000 0.00 0.00 0.00  1 0.00  0 0.00 0.00
#&gt; TCGA.RW.A68A.01     6  0.0000      0.000 0.00 0.00 0.00  0 0.00  1 0.00 0.00
#&gt; TCGA.WB.A80K.01     3  0.2114      0.706 0.00 0.00 0.84  0 0.00  0 0.00 0.16
#&gt; TCGA.QT.A5XM.01     1  0.0000      0.866 1.00 0.00 0.00  0 0.00  0 0.00 0.00
#&gt; TCGA.QR.A70X.01     5  0.0000      0.982 0.00 0.00 0.00  0 1.00  0 0.00 0.00
#&gt; TCGA.WB.A81H.01     5  0.0000      0.982 0.00 0.00 0.00  0 1.00  0 0.00 0.00
#&gt; TCGA.SR.A6MV.01     2  0.0471      0.889 0.00 0.98 0.00  0 0.02  0 0.00 0.00
#&gt; TCGA.PR.A5PH.01     3  0.0808      0.740 0.00 0.00 0.96  0 0.00  0 0.00 0.04
#&gt; TCGA.RW.A686.06     8  0.2756      1.000 0.00 0.00 0.26  0 0.00  0 0.00 0.74
#&gt; TCGA.SQ.A6I4.01     1  0.0000      0.866 1.00 0.00 0.00  0 0.00  0 0.00 0.00
#&gt; TCGA.WB.A821.01     2  0.0471      0.889 0.00 0.98 0.00  0 0.02  0 0.00 0.00
#&gt; TCGA.SP.A6QK.01     5  0.0471      0.982 0.00 0.02 0.00  0 0.98  0 0.00 0.00
#&gt; TCGA.WB.A817.01     1  0.3021      0.861 0.80 0.02 0.00  0 0.00  0 0.02 0.16
#&gt; TCGA.RW.A7D0.01     5  0.0471      0.982 0.00 0.02 0.00  0 0.98  0 0.00 0.00
#&gt; TCGA.SP.A6QC.01     1  0.0000      0.866 1.00 0.00 0.00  0 0.00  0 0.00 0.00
#&gt; TCGA.WB.A81V.01     1  0.3303      0.850 0.76 0.02 0.00  0 0.00  0 0.02 0.20
#&gt; TCGA.WB.A81N.01     2  0.3404      0.659 0.00 0.72 0.00  0 0.24  0 0.00 0.04
#&gt; TCGA.RW.A686.01     8  0.2756      1.000 0.00 0.00 0.26  0 0.00  0 0.00 0.74
</code></pre>

<script>
$('#tab-node-032-get-classes-7-a').parent().next().next().hide();
$('#tab-node-032-get-classes-7-a').click(function(){
  $('#tab-node-032-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-032-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-032-consensus-heatmap'>
<ul>
<li><a href='#tab-node-032-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-032-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-032-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-032-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-032-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-032-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-032-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-032-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-032-membership-heatmap'>
<ul>
<li><a href='#tab-node-032-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-032-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-032-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-032-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-032-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-032-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-032-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-1-1.png" alt="plot of chunk tab-node-032-membership-heatmap-1"/></p>

</div>
<div id='tab-node-032-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-2-1.png" alt="plot of chunk tab-node-032-membership-heatmap-2"/></p>

</div>
<div id='tab-node-032-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-3-1.png" alt="plot of chunk tab-node-032-membership-heatmap-3"/></p>

</div>
<div id='tab-node-032-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-4-1.png" alt="plot of chunk tab-node-032-membership-heatmap-4"/></p>

</div>
<div id='tab-node-032-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-5-1.png" alt="plot of chunk tab-node-032-membership-heatmap-5"/></p>

</div>
<div id='tab-node-032-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-6-1.png" alt="plot of chunk tab-node-032-membership-heatmap-6"/></p>

</div>
<div id='tab-node-032-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-7-1.png" alt="plot of chunk tab-node-032-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-032-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-032-get-signatures'>
<ul>
<li><a href='#tab-node-032-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-032-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-032-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-032-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-032-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-032-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-032-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-1-1.png" alt="plot of chunk tab-node-032-get-signatures-1"/></p>

</div>
<div id='tab-node-032-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-2-1.png" alt="plot of chunk tab-node-032-get-signatures-2"/></p>

</div>
<div id='tab-node-032-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-3-1.png" alt="plot of chunk tab-node-032-get-signatures-3"/></p>

</div>
<div id='tab-node-032-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-4-1.png" alt="plot of chunk tab-node-032-get-signatures-4"/></p>

</div>
<div id='tab-node-032-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-5-1.png" alt="plot of chunk tab-node-032-get-signatures-5"/></p>

</div>
<div id='tab-node-032-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-6-1.png" alt="plot of chunk tab-node-032-get-signatures-6"/></p>

</div>
<div id='tab-node-032-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-7-1.png" alt="plot of chunk tab-node-032-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-032-signature_compare](figure_cola/node-032-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-032-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-032-dimension-reduction'>
<ul>
<li><a href='#tab-node-032-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-032-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-032-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-032-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-032-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-032-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-032-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-1-1.png" alt="plot of chunk tab-node-032-dimension-reduction-1"/></p>

</div>
<div id='tab-node-032-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-2-1.png" alt="plot of chunk tab-node-032-dimension-reduction-2"/></p>

</div>
<div id='tab-node-032-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-3-1.png" alt="plot of chunk tab-node-032-dimension-reduction-3"/></p>

</div>
<div id='tab-node-032-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-4-1.png" alt="plot of chunk tab-node-032-dimension-reduction-4"/></p>

</div>
<div id='tab-node-032-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-5-1.png" alt="plot of chunk tab-node-032-dimension-reduction-5"/></p>

</div>
<div id='tab-node-032-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-6-1.png" alt="plot of chunk tab-node-032-dimension-reduction-6"/></p>

</div>
<div id='tab-node-032-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-7-1.png" alt="plot of chunk tab-node-032-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-032-collect-classes](figure_cola/node-032-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node04


Parent node: [Node0](#Node0).
Child nodes: 
                Node011-leaf
        ,
                [Node012](#Node012)
        ,
                [Node013](#Node013)
        ,
                Node021-leaf
        ,
                [Node022](#Node022)
        ,
                Node023-leaf
        ,
                Node024-leaf
        ,
                [Node031](#Node031)
        ,
                [Node032](#Node032)
        ,
                Node033-leaf
        ,
                [Node041](#Node041)
        ,
                Node042-leaf
        ,
                Node043-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["04"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 34 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-04-collect-plots](figure_cola/node-04-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-04-select-partition-number](figure_cola/node-04-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5139 0.487   0.487
#> 3 3 1.000           0.979       0.987         0.1896 0.863   0.730
#> 4 4 0.768           0.886       0.906         0.1709 0.850   0.638
#> 5 5 0.772           0.782       0.851         0.0864 0.873   0.587
#> 6 6 0.758           0.687       0.831         0.0464 0.923   0.669
#> 7 7 0.796           0.751       0.822         0.0437 0.902   0.530
#> 8 8 0.845           0.832       0.862         0.0283 0.966   0.759
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-04-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-04-get-classes'>
<ul>
<li><a href='#tab-node-04-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-04-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-04-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-04-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-04-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-04-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-04-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-04-get-classes-1'>
<p><a id='tab-node-04-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.RW.A68D.01     2       0          1  0  1
#&gt; TCGA.RT.A6Y9.01     2       0          1  0  1
#&gt; TCGA.QR.A7IN.01     2       0          1  0  1
#&gt; TCGA.S7.A7X1.01     1       0          1  1  0
#&gt; TCGA.QT.A7U0.01     2       0          1  0  1
#&gt; TCGA.RW.A68C.01     1       0          1  1  0
#&gt; TCGA.TT.A6YP.01     1       0          1  1  0
#&gt; TCGA.RW.A67X.01     1       0          1  1  0
#&gt; TCGA.SP.A6QH.01     1       0          1  1  0
#&gt; TCGA.QR.A706.01     1       0          1  1  0
#&gt; TCGA.QR.A6GZ.05     1       0          1  1  0
#&gt; TCGA.QR.A70A.01     2       0          1  0  1
#&gt; TCGA.S7.A7WV.01     1       0          1  1  0
#&gt; TCGA.QR.A708.01     2       0          1  0  1
#&gt; TCGA.SR.A6N0.01     2       0          1  0  1
#&gt; TCGA.W2.A7HH.01     2       0          1  0  1
#&gt; TCGA.S7.A7WQ.01     1       0          1  1  0
#&gt; TCGA.P8.A6RY.01     2       0          1  0  1
#&gt; TCGA.SR.A6MR.01     2       0          1  0  1
#&gt; TCGA.S7.A7X0.01     1       0          1  1  0
#&gt; TCGA.TT.A6YK.01     1       0          1  1  0
#&gt; TCGA.QR.A70N.01     1       0          1  1  0
#&gt; TCGA.QR.A70J.01     1       0          1  1  0
#&gt; TCGA.W2.A7UY.01     1       0          1  1  0
#&gt; TCGA.QR.A6H5.01     1       0          1  1  0
#&gt; TCGA.SA.A6C2.01     2       0          1  0  1
#&gt; TCGA.SR.A6MT.01     2       0          1  0  1
#&gt; TCGA.S7.A7WW.01     2       0          1  0  1
#&gt; TCGA.QR.A70T.01     2       0          1  0  1
#&gt; TCGA.P8.A5KC.01     1       0          1  1  0
#&gt; TCGA.QR.A6GX.01     1       0          1  1  0
#&gt; TCGA.QT.A5XL.01     1       0          1  1  0
#&gt; TCGA.WB.A81A.01     2       0          1  0  1
#&gt; TCGA.QR.A70E.01     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-04-get-classes-1-a').parent().next().next().hide();
$('#tab-node-04-get-classes-1-a').click(function(){
  $('#tab-node-04-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-04-get-classes-2'>
<p><a id='tab-node-04-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.RW.A68D.01     3  0.0892      1.000 0.00 0.02 0.98
#&gt; TCGA.RT.A6Y9.01     3  0.0892      1.000 0.00 0.02 0.98
#&gt; TCGA.QR.A7IN.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.S7.A7X1.01     1  0.0892      0.981 0.98 0.00 0.02
#&gt; TCGA.QT.A7U0.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.RW.A68C.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.TT.A6YP.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.RW.A67X.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.QR.A706.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     1  0.0892      0.981 0.98 0.00 0.02
#&gt; TCGA.QR.A70A.01     3  0.0892      1.000 0.00 0.02 0.98
#&gt; TCGA.S7.A7WV.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.QR.A708.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.SR.A6N0.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.W2.A7HH.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.S7.A7WQ.01     1  0.0892      0.981 0.98 0.00 0.02
#&gt; TCGA.P8.A6RY.01     2  0.3340      0.858 0.00 0.88 0.12
#&gt; TCGA.SR.A6MR.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.S7.A7X0.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.TT.A6YK.01     1  0.2959      0.873 0.90 0.10 0.00
#&gt; TCGA.QR.A70N.01     1  0.0892      0.981 0.98 0.00 0.02
#&gt; TCGA.QR.A70J.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     1  0.0892      0.981 0.98 0.00 0.02
#&gt; TCGA.QR.A6H5.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.SR.A6MT.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.S7.A7WW.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.QR.A70T.01     3  0.0892      1.000 0.00 0.02 0.98
#&gt; TCGA.P8.A5KC.01     1  0.0000      0.986 1.00 0.00 0.00
#&gt; TCGA.QR.A6GX.01     2  0.0892      0.965 0.02 0.98 0.00
#&gt; TCGA.QT.A5XL.01     1  0.0892      0.981 0.98 0.00 0.02
#&gt; TCGA.WB.A81A.01     2  0.0000      0.987 0.00 1.00 0.00
#&gt; TCGA.QR.A70E.01     2  0.0000      0.987 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-04-get-classes-2-a').parent().next().next().hide();
$('#tab-node-04-get-classes-2-a').click(function(){
  $('#tab-node-04-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-04-get-classes-3'>
<p><a id='tab-node-04-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.RW.A68D.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.RT.A6Y9.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.QR.A7IN.01     4  0.1637      0.842 0.00 0.06 0.00 0.94
#&gt; TCGA.S7.A7X1.01     1  0.2345      0.908 0.90 0.10 0.00 0.00
#&gt; TCGA.QT.A7U0.01     4  0.0000      0.837 0.00 0.00 0.00 1.00
#&gt; TCGA.RW.A68C.01     1  0.0000      0.915 1.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YP.01     1  0.0000      0.915 1.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67X.01     1  0.0000      0.915 1.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     1  0.2011      0.885 0.92 0.08 0.00 0.00
#&gt; TCGA.QR.A706.01     1  0.4227      0.884 0.82 0.12 0.00 0.06
#&gt; TCGA.QR.A6GZ.05     4  0.4610      0.695 0.10 0.10 0.00 0.80
#&gt; TCGA.QR.A70A.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7WV.01     1  0.2011      0.885 0.92 0.08 0.00 0.00
#&gt; TCGA.QR.A708.01     2  0.3400      0.933 0.00 0.82 0.00 0.18
#&gt; TCGA.SR.A6N0.01     4  0.1637      0.842 0.00 0.06 0.00 0.94
#&gt; TCGA.W2.A7HH.01     2  0.4522      0.816 0.00 0.68 0.00 0.32
#&gt; TCGA.S7.A7WQ.01     1  0.2345      0.908 0.90 0.10 0.00 0.00
#&gt; TCGA.P8.A6RY.01     2  0.4079      0.920 0.00 0.80 0.02 0.18
#&gt; TCGA.SR.A6MR.01     4  0.2011      0.827 0.00 0.08 0.00 0.92
#&gt; TCGA.S7.A7X0.01     1  0.0707      0.912 0.98 0.02 0.00 0.00
#&gt; TCGA.TT.A6YK.01     4  0.4581      0.699 0.08 0.12 0.00 0.80
#&gt; TCGA.QR.A70N.01     1  0.2345      0.908 0.90 0.10 0.00 0.00
#&gt; TCGA.QR.A70J.01     1  0.2011      0.885 0.92 0.08 0.00 0.00
#&gt; TCGA.W2.A7UY.01     1  0.4292      0.873 0.82 0.10 0.00 0.08
#&gt; TCGA.QR.A6H5.01     1  0.0000      0.915 1.00 0.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     2  0.4522      0.816 0.00 0.68 0.00 0.32
#&gt; TCGA.SR.A6MT.01     2  0.3400      0.933 0.00 0.82 0.00 0.18
#&gt; TCGA.S7.A7WW.01     4  0.2011      0.827 0.00 0.08 0.00 0.92
#&gt; TCGA.QR.A70T.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.P8.A5KC.01     1  0.4581      0.872 0.80 0.12 0.00 0.08
#&gt; TCGA.QR.A6GX.01     4  0.1211      0.827 0.00 0.04 0.00 0.96
#&gt; TCGA.QT.A5XL.01     1  0.4292      0.873 0.82 0.10 0.00 0.08
#&gt; TCGA.WB.A81A.01     2  0.3400      0.933 0.00 0.82 0.00 0.18
#&gt; TCGA.QR.A70E.01     2  0.3400      0.933 0.00 0.82 0.00 0.18
</code></pre>

<script>
$('#tab-node-04-get-classes-3-a').parent().next().next().hide();
$('#tab-node-04-get-classes-3-a').click(function(){
  $('#tab-node-04-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-04-get-classes-4'>
<p><a id='tab-node-04-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.RW.A68D.01     3   0.000      1.000 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.RT.A6Y9.01     3   0.000      1.000 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A7IN.01     4   0.104      0.949 0.00 0.04 0.00 0.96 0.00
#&gt; TCGA.S7.A7X1.01     1   0.141      0.842 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.QT.A7U0.01     4   0.104      0.916 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.RW.A68C.01     1   0.000      0.879 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YP.01     1   0.000      0.879 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67X.01     1   0.000      0.879 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     1   0.373      0.767 0.80 0.00 0.00 0.04 0.16
#&gt; TCGA.QR.A706.01     5   0.430      0.498 0.48 0.00 0.00 0.00 0.52
#&gt; TCGA.QR.A6GZ.05     5   0.615      0.497 0.20 0.00 0.00 0.24 0.56
#&gt; TCGA.QR.A70A.01     3   0.000      1.000 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.S7.A7WV.01     1   0.373      0.767 0.80 0.00 0.00 0.04 0.16
#&gt; TCGA.QR.A708.01     2   0.342      0.792 0.00 0.76 0.00 0.00 0.24
#&gt; TCGA.SR.A6N0.01     4   0.165      0.953 0.00 0.04 0.00 0.94 0.02
#&gt; TCGA.W2.A7HH.01     2   0.543      0.703 0.00 0.60 0.00 0.08 0.32
#&gt; TCGA.S7.A7WQ.01     1   0.141      0.842 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.P8.A6RY.01     2   0.104      0.793 0.00 0.96 0.04 0.00 0.00
#&gt; TCGA.SR.A6MR.01     4   0.244      0.946 0.00 0.04 0.00 0.90 0.06
#&gt; TCGA.S7.A7X0.01     1   0.165      0.858 0.94 0.00 0.00 0.04 0.02
#&gt; TCGA.TT.A6YK.01     5   0.329      0.372 0.04 0.00 0.00 0.12 0.84
#&gt; TCGA.QR.A70N.01     1   0.141      0.842 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.QR.A70J.01     1   0.373      0.767 0.80 0.00 0.00 0.04 0.16
#&gt; TCGA.W2.A7UY.01     5   0.517      0.565 0.46 0.00 0.00 0.04 0.50
#&gt; TCGA.QR.A6H5.01     1   0.000      0.879 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     2   0.543      0.703 0.00 0.60 0.00 0.08 0.32
#&gt; TCGA.SR.A6MT.01     2   0.000      0.818 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WW.01     4   0.244      0.946 0.00 0.04 0.00 0.90 0.06
#&gt; TCGA.QR.A70T.01     3   0.000      1.000 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.P8.A5KC.01     5   0.516      0.568 0.44 0.00 0.00 0.04 0.52
#&gt; TCGA.QR.A6GX.01     5   0.443      0.167 0.00 0.06 0.00 0.20 0.74
#&gt; TCGA.QT.A5XL.01     5   0.517      0.565 0.46 0.00 0.00 0.04 0.50
#&gt; TCGA.WB.A81A.01     2   0.173      0.825 0.00 0.92 0.00 0.00 0.08
#&gt; TCGA.QR.A70E.01     2   0.000      0.818 0.00 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-04-get-classes-4-a').parent().next().next().hide();
$('#tab-node-04-get-classes-4-a').click(function(){
  $('#tab-node-04-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-04-get-classes-5'>
<p><a id='tab-node-04-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6
#&gt; TCGA.RW.A68D.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.RT.A6Y9.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.QR.A7IN.01     4  0.1556      0.940 0.00 0.00  0 0.92 0.08 0.00
#&gt; TCGA.S7.A7X1.01     1  0.2048      0.631 0.88 0.00  0 0.00 0.12 0.00
#&gt; TCGA.QT.A7U0.01     4  0.1814      0.928 0.00 0.00  0 0.90 0.10 0.00
#&gt; TCGA.RW.A68C.01     1  0.0000      0.714 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.TT.A6YP.01     1  0.0000      0.714 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.RW.A67X.01     1  0.0000      0.714 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     1  0.4989      0.536 0.64 0.00  0 0.00 0.14 0.22
#&gt; TCGA.QR.A706.01     1  0.4873     -0.478 0.52 0.00  0 0.00 0.42 0.06
#&gt; TCGA.QR.A6GZ.05     5  0.2981      0.704 0.16 0.00  0 0.00 0.82 0.02
#&gt; TCGA.QR.A70A.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.S7.A7WV.01     1  0.4989      0.536 0.64 0.00  0 0.00 0.14 0.22
#&gt; TCGA.QR.A708.01     6  0.4482      0.367 0.00 0.36  0 0.00 0.04 0.60
#&gt; TCGA.SR.A6N0.01     4  0.0000      0.961 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     6  0.4121      0.633 0.00 0.22  0 0.06 0.00 0.72
#&gt; TCGA.S7.A7WQ.01     1  0.2048      0.631 0.88 0.00  0 0.00 0.12 0.00
#&gt; TCGA.P8.A6RY.01     2  0.0547      0.790 0.00 0.98  0 0.02 0.00 0.00
#&gt; TCGA.SR.A6MR.01     4  0.0000      0.961 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.S7.A7X0.01     1  0.2956      0.617 0.84 0.00  0 0.00 0.04 0.12
#&gt; TCGA.TT.A6YK.01     6  0.4845      0.285 0.00 0.00  0 0.06 0.40 0.54
#&gt; TCGA.QR.A70N.01     1  0.2048      0.631 0.88 0.00  0 0.00 0.12 0.00
#&gt; TCGA.QR.A70J.01     1  0.4989      0.536 0.64 0.00  0 0.00 0.14 0.22
#&gt; TCGA.W2.A7UY.01     5  0.3409      0.823 0.30 0.00  0 0.00 0.70 0.00
#&gt; TCGA.QR.A6H5.01     1  0.0000      0.714 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     6  0.4121      0.633 0.00 0.22  0 0.06 0.00 0.72
#&gt; TCGA.SR.A6MT.01     2  0.0000      0.804 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.S7.A7WW.01     4  0.0000      0.961 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.QR.A70T.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.P8.A5KC.01     5  0.4758      0.796 0.36 0.00  0 0.00 0.58 0.06
#&gt; TCGA.QR.A6GX.01     6  0.3997      0.606 0.00 0.02  0 0.06 0.14 0.78
#&gt; TCGA.QT.A5XL.01     5  0.4144      0.816 0.36 0.00  0 0.00 0.62 0.02
#&gt; TCGA.WB.A81A.01     2  0.4534      0.064 0.00 0.58  0 0.00 0.04 0.38
#&gt; TCGA.QR.A70E.01     2  0.0000      0.804 0.00 1.00  0 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-04-get-classes-5-a').parent().next().next().hide();
$('#tab-node-04-get-classes-5-a').click(function(){
  $('#tab-node-04-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-04-get-classes-6'>
<p><a id='tab-node-04-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6   p7
#&gt; TCGA.RW.A68D.01     3   0.000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.RT.A6Y9.01     3   0.000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A7IN.01     4   0.394     0.8603 0.00 0.06  0 0.78 0.08 0.00 0.08
#&gt; TCGA.S7.A7X1.01     1   0.283     0.7536 0.84 0.00  0 0.00 0.08 0.00 0.08
#&gt; TCGA.QT.A7U0.01     4   0.394     0.8603 0.00 0.06  0 0.78 0.08 0.00 0.08
#&gt; TCGA.RW.A68C.01     1   0.000     0.7625 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YP.01     1   0.000     0.7625 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67X.01     1   0.000     0.7625 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     7   0.350     1.0000 0.42 0.00  0 0.00 0.00 0.00 0.58
#&gt; TCGA.QR.A706.01     5   0.346     0.2331 0.40 0.00  0 0.00 0.60 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     5   0.546     0.5170 0.06 0.12  0 0.00 0.60 0.00 0.22
#&gt; TCGA.QR.A70A.01     3   0.000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WV.01     7   0.350     1.0000 0.42 0.00  0 0.00 0.00 0.00 0.58
#&gt; TCGA.QR.A708.01     6   0.193     0.7804 0.00 0.02  0 0.00 0.00 0.90 0.08
#&gt; TCGA.SR.A6N0.01     4   0.000     0.9090 0.00 0.00  0 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     6   0.000     0.8114 0.00 0.00  0 0.00 0.00 1.00 0.00
#&gt; TCGA.S7.A7WQ.01     1   0.283     0.7536 0.84 0.00  0 0.00 0.08 0.00 0.08
#&gt; TCGA.P8.A6RY.01     2   0.275     0.9684 0.00 0.82  0 0.02 0.00 0.16 0.00
#&gt; TCGA.SR.A6MR.01     4   0.000     0.9090 0.00 0.00  0 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7X0.01     1   0.467     0.0212 0.52 0.00  0 0.00 0.40 0.00 0.08
#&gt; TCGA.TT.A6YK.01     5   0.427    -0.0610 0.00 0.00  0 0.00 0.52 0.44 0.04
#&gt; TCGA.QR.A70N.01     1   0.283     0.7536 0.84 0.00  0 0.00 0.08 0.00 0.08
#&gt; TCGA.QR.A70J.01     7   0.350     1.0000 0.42 0.00  0 0.00 0.00 0.00 0.58
#&gt; TCGA.W2.A7UY.01     5   0.568     0.5259 0.08 0.12  0 0.00 0.58 0.00 0.22
#&gt; TCGA.QR.A6H5.01     1   0.000     0.7625 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     6   0.000     0.8114 0.00 0.00  0 0.00 0.00 1.00 0.00
#&gt; TCGA.SR.A6MT.01     2   0.242     0.9840 0.00 0.82  0 0.00 0.00 0.18 0.00
#&gt; TCGA.S7.A7WW.01     4   0.000     0.9090 0.00 0.00  0 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70T.01     3   0.000     1.0000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KC.01     5   0.283     0.5264 0.24 0.00  0 0.00 0.76 0.00 0.00
#&gt; TCGA.QR.A6GX.01     6   0.309     0.6458 0.00 0.00  0 0.00 0.16 0.80 0.04
#&gt; TCGA.QT.A5XL.01     5   0.435     0.5407 0.24 0.10  0 0.00 0.66 0.00 0.00
#&gt; TCGA.WB.A81A.01     6   0.403     0.4919 0.00 0.22  0 0.00 0.00 0.70 0.08
#&gt; TCGA.QR.A70E.01     2   0.242     0.9840 0.00 0.82  0 0.00 0.00 0.18 0.00
</code></pre>

<script>
$('#tab-node-04-get-classes-6-a').parent().next().next().hide();
$('#tab-node-04-get-classes-6-a').click(function(){
  $('#tab-node-04-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-04-get-classes-7'>
<p><a id='tab-node-04-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6   p7   p8
#&gt; TCGA.RW.A68D.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RT.A6Y9.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A7IN.01     4  0.4728      0.756 0.00 0.04  0 0.66 0.02 0.00 0.22 0.06
#&gt; TCGA.S7.A7X1.01     1  0.3227      0.768 0.78 0.00  0 0.00 0.08 0.00 0.00 0.14
#&gt; TCGA.QT.A7U0.01     4  0.4728      0.756 0.00 0.04  0 0.66 0.02 0.00 0.22 0.06
#&gt; TCGA.RW.A68C.01     1  0.0000      0.800 1.00 0.00  0 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YP.01     1  0.0000      0.800 1.00 0.00  0 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67X.01     1  0.0000      0.800 1.00 0.00  0 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SP.A6QH.01     7  0.3237      1.000 0.40 0.00  0 0.00 0.00 0.00 0.60 0.00
#&gt; TCGA.QR.A706.01     5  0.3551      0.615 0.22 0.00  0 0.00 0.72 0.00 0.00 0.06
#&gt; TCGA.QR.A6GZ.05     8  0.1557      0.950 0.00 0.00  0 0.00 0.06 0.00 0.02 0.92
#&gt; TCGA.QR.A70A.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WV.01     7  0.3237      1.000 0.40 0.00  0 0.00 0.00 0.00 0.60 0.00
#&gt; TCGA.QR.A708.01     6  0.2265      0.847 0.00 0.02  0 0.00 0.02 0.88 0.08 0.00
#&gt; TCGA.SR.A6N0.01     4  0.0000      0.845 0.00 0.00  0 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7HH.01     6  0.0808      0.867 0.00 0.00  0 0.00 0.04 0.96 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     1  0.3227      0.768 0.78 0.00  0 0.00 0.08 0.00 0.00 0.14
#&gt; TCGA.P8.A6RY.01     2  0.0808      1.000 0.00 0.96  0 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.SR.A6MR.01     4  0.0000      0.845 0.00 0.00  0 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7X0.01     5  0.3746      0.509 0.32 0.00  0 0.00 0.64 0.00 0.04 0.00
#&gt; TCGA.TT.A6YK.01     5  0.2025      0.454 0.00 0.00  0 0.00 0.88 0.10 0.02 0.00
#&gt; TCGA.QR.A70N.01     1  0.3227      0.768 0.78 0.00  0 0.00 0.08 0.00 0.00 0.14
#&gt; TCGA.QR.A70J.01     7  0.3237      1.000 0.40 0.00  0 0.00 0.00 0.00 0.60 0.00
#&gt; TCGA.W2.A7UY.01     8  0.1887      0.950 0.00 0.00  0 0.00 0.06 0.00 0.04 0.90
#&gt; TCGA.QR.A6H5.01     1  0.0000      0.800 1.00 0.00  0 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SA.A6C2.01     6  0.0808      0.867 0.00 0.00  0 0.00 0.04 0.96 0.00 0.00
#&gt; TCGA.SR.A6MT.01     2  0.0808      1.000 0.00 0.96  0 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.S7.A7WW.01     4  0.0000      0.845 0.00 0.00  0 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70T.01     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KC.01     5  0.3198      0.583 0.02 0.00  0 0.00 0.72 0.00 0.00 0.26
#&gt; TCGA.QR.A6GX.01     6  0.3291      0.695 0.00 0.00  0 0.00 0.28 0.70 0.02 0.00
#&gt; TCGA.QT.A5XL.01     5  0.3374      0.550 0.02 0.00  0 0.00 0.68 0.00 0.00 0.30
#&gt; TCGA.WB.A81A.01     6  0.2025      0.847 0.00 0.02  0 0.00 0.00 0.88 0.10 0.00
#&gt; TCGA.QR.A70E.01     2  0.0808      1.000 0.00 0.96  0 0.00 0.00 0.04 0.00 0.00
</code></pre>

<script>
$('#tab-node-04-get-classes-7-a').parent().next().next().hide();
$('#tab-node-04-get-classes-7-a').click(function(){
  $('#tab-node-04-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-04-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-04-consensus-heatmap'>
<ul>
<li><a href='#tab-node-04-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-04-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-04-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-04-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-04-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-04-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-04-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-04-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-04-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-04-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-04-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-04-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-04-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-04-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-04-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-04-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-04-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-04-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-04-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-04-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-04-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-04-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-04-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-04-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-04-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-04-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-04-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-04-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-04-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-04-membership-heatmap'>
<ul>
<li><a href='#tab-node-04-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-04-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-04-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-04-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-04-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-04-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-04-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-04-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-04-membership-heatmap-1-1.png" alt="plot of chunk tab-node-04-membership-heatmap-1"/></p>

</div>
<div id='tab-node-04-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-04-membership-heatmap-2-1.png" alt="plot of chunk tab-node-04-membership-heatmap-2"/></p>

</div>
<div id='tab-node-04-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-04-membership-heatmap-3-1.png" alt="plot of chunk tab-node-04-membership-heatmap-3"/></p>

</div>
<div id='tab-node-04-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-04-membership-heatmap-4-1.png" alt="plot of chunk tab-node-04-membership-heatmap-4"/></p>

</div>
<div id='tab-node-04-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-04-membership-heatmap-5-1.png" alt="plot of chunk tab-node-04-membership-heatmap-5"/></p>

</div>
<div id='tab-node-04-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-04-membership-heatmap-6-1.png" alt="plot of chunk tab-node-04-membership-heatmap-6"/></p>

</div>
<div id='tab-node-04-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-04-membership-heatmap-7-1.png" alt="plot of chunk tab-node-04-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-04-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-04-get-signatures'>
<ul>
<li><a href='#tab-node-04-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-04-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-04-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-04-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-04-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-04-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-04-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-04-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-04-get-signatures-1-1.png" alt="plot of chunk tab-node-04-get-signatures-1"/></p>

</div>
<div id='tab-node-04-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-04-get-signatures-2-1.png" alt="plot of chunk tab-node-04-get-signatures-2"/></p>

</div>
<div id='tab-node-04-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-04-get-signatures-3-1.png" alt="plot of chunk tab-node-04-get-signatures-3"/></p>

</div>
<div id='tab-node-04-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-04-get-signatures-4-1.png" alt="plot of chunk tab-node-04-get-signatures-4"/></p>

</div>
<div id='tab-node-04-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-04-get-signatures-5-1.png" alt="plot of chunk tab-node-04-get-signatures-5"/></p>

</div>
<div id='tab-node-04-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-04-get-signatures-6-1.png" alt="plot of chunk tab-node-04-get-signatures-6"/></p>

</div>
<div id='tab-node-04-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-04-get-signatures-7-1.png" alt="plot of chunk tab-node-04-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-04-signature_compare](figure_cola/node-04-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-04-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-04-dimension-reduction'>
<ul>
<li><a href='#tab-node-04-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-04-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-04-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-04-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-04-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-04-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-04-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-04-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-04-dimension-reduction-1-1.png" alt="plot of chunk tab-node-04-dimension-reduction-1"/></p>

</div>
<div id='tab-node-04-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-04-dimension-reduction-2-1.png" alt="plot of chunk tab-node-04-dimension-reduction-2"/></p>

</div>
<div id='tab-node-04-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-04-dimension-reduction-3-1.png" alt="plot of chunk tab-node-04-dimension-reduction-3"/></p>

</div>
<div id='tab-node-04-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-04-dimension-reduction-4-1.png" alt="plot of chunk tab-node-04-dimension-reduction-4"/></p>

</div>
<div id='tab-node-04-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-04-dimension-reduction-5-1.png" alt="plot of chunk tab-node-04-dimension-reduction-5"/></p>

</div>
<div id='tab-node-04-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-04-dimension-reduction-6-1.png" alt="plot of chunk tab-node-04-dimension-reduction-6"/></p>

</div>
<div id='tab-node-04-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-04-dimension-reduction-7-1.png" alt="plot of chunk tab-node-04-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-04-collect-classes](figure_cola/node-04-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node041


Parent node: [Node04](#Node04).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0311-leaf
        ,
                Node0312-leaf
        ,
                Node0313-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0411-leaf
        ,
                Node0412-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["041"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 17 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-041-collect-plots](figure_cola/node-041-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-041-select-partition-number](figure_cola/node-041-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5299 0.471   0.471
#> 3 3 0.868           0.907       0.972         0.1148 0.949   0.891
#> 4 4 0.765           0.656       0.882         0.1523 0.941   0.860
#> 5 5 0.713           0.658       0.885         0.0747 0.949   0.857
#> 6 6 0.699           0.597       0.838         0.0631 1.000   1.000
#> 7 7 0.706           0.429       0.748         0.0556 0.926   0.762
#> 8 8 0.728           0.360       0.724         0.0427 0.956   0.818
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-041-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-041-get-classes'>
<ul>
<li><a href='#tab-node-041-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-041-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-041-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-041-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-041-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-041-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-041-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-041-get-classes-1'>
<p><a id='tab-node-041-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.S7.A7X1.01     2       0          1  0  1
#&gt; TCGA.RW.A68C.01     2       0          1  0  1
#&gt; TCGA.TT.A6YP.01     1       0          1  1  0
#&gt; TCGA.RW.A67X.01     2       0          1  0  1
#&gt; TCGA.SP.A6QH.01     1       0          1  1  0
#&gt; TCGA.QR.A706.01     1       0          1  1  0
#&gt; TCGA.QR.A6GZ.05     2       0          1  0  1
#&gt; TCGA.S7.A7WV.01     1       0          1  1  0
#&gt; TCGA.S7.A7WQ.01     2       0          1  0  1
#&gt; TCGA.S7.A7X0.01     1       0          1  1  0
#&gt; TCGA.TT.A6YK.01     2       0          1  0  1
#&gt; TCGA.QR.A70N.01     2       0          1  0  1
#&gt; TCGA.QR.A70J.01     1       0          1  1  0
#&gt; TCGA.W2.A7UY.01     1       0          1  1  0
#&gt; TCGA.QR.A6H5.01     1       0          1  1  0
#&gt; TCGA.P8.A5KC.01     2       0          1  0  1
#&gt; TCGA.QT.A5XL.01     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-041-get-classes-1-a').parent().next().next().hide();
$('#tab-node-041-get-classes-1-a').click(function(){
  $('#tab-node-041-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-041-get-classes-2'>
<p><a id='tab-node-041-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.S7.A7X1.01     2  0.0000      0.963 0.00 1.00 0.00
#&gt; TCGA.RW.A68C.01     2  0.0892      0.961 0.00 0.98 0.02
#&gt; TCGA.TT.A6YP.01     1  0.0892      0.976 0.98 0.00 0.02
#&gt; TCGA.RW.A67X.01     2  0.0000      0.963 0.00 1.00 0.00
#&gt; TCGA.SP.A6QH.01     1  0.0000      0.996 1.00 0.00 0.00
#&gt; TCGA.QR.A706.01     1  0.0000      0.996 1.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     2  0.2537      0.911 0.00 0.92 0.08
#&gt; TCGA.S7.A7WV.01     1  0.0000      0.996 1.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     2  0.0000      0.963 0.00 1.00 0.00
#&gt; TCGA.S7.A7X0.01     1  0.0000      0.996 1.00 0.00 0.00
#&gt; TCGA.TT.A6YK.01     2  0.4291      0.825 0.00 0.82 0.18
#&gt; TCGA.QR.A70N.01     2  0.0000      0.963 0.00 1.00 0.00
#&gt; TCGA.QR.A70J.01     1  0.0000      0.996 1.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     3  0.3686      0.000 0.14 0.00 0.86
#&gt; TCGA.QR.A6H5.01     1  0.0000      0.996 1.00 0.00 0.00
#&gt; TCGA.P8.A5KC.01     2  0.0892      0.961 0.00 0.98 0.02
#&gt; TCGA.QT.A5XL.01     2  0.0892      0.961 0.00 0.98 0.02
</code></pre>

<script>
$('#tab-node-041-get-classes-2-a').parent().next().next().hide();
$('#tab-node-041-get-classes-2-a').click(function(){
  $('#tab-node-041-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-041-get-classes-3'>
<p><a id='tab-node-041-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.S7.A7X1.01     2  0.1637      0.630 0.00 0.94 0.00 0.06
#&gt; TCGA.RW.A68C.01     2  0.3172      0.555 0.00 0.84 0.00 0.16
#&gt; TCGA.TT.A6YP.01     1  0.0707      0.979 0.98 0.00 0.02 0.00
#&gt; TCGA.RW.A67X.01     2  0.2647      0.622 0.00 0.88 0.00 0.12
#&gt; TCGA.SP.A6QH.01     1  0.0000      0.993 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A706.01     1  0.0000      0.993 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     2  0.5487      0.341 0.00 0.58 0.02 0.40
#&gt; TCGA.S7.A7WV.01     1  0.0000      0.993 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     2  0.3853      0.589 0.00 0.82 0.02 0.16
#&gt; TCGA.S7.A7X0.01     1  0.0000      0.993 1.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YK.01     4  0.4624      0.000 0.00 0.34 0.00 0.66
#&gt; TCGA.QR.A70N.01     2  0.3801      0.527 0.00 0.78 0.00 0.22
#&gt; TCGA.QR.A70J.01     1  0.0000      0.993 1.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     3  0.0707      0.000 0.02 0.00 0.98 0.00
#&gt; TCGA.QR.A6H5.01     1  0.0707      0.979 0.98 0.00 0.02 0.00
#&gt; TCGA.P8.A5KC.01     2  0.3975      0.441 0.00 0.76 0.00 0.24
#&gt; TCGA.QT.A5XL.01     2  0.3610      0.532 0.00 0.80 0.00 0.20
</code></pre>

<script>
$('#tab-node-041-get-classes-3-a').parent().next().next().hide();
$('#tab-node-041-get-classes-3-a').click(function(){
  $('#tab-node-041-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-041-get-classes-4'>
<p><a id='tab-node-041-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.S7.A7X1.01     2  0.3106      0.716 0.00 0.84 0.00 0.02 0.14
#&gt; TCGA.RW.A68C.01     2  0.2438      0.737 0.00 0.90 0.00 0.06 0.04
#&gt; TCGA.TT.A6YP.01     1  0.2927      0.892 0.88 0.00 0.08 0.02 0.02
#&gt; TCGA.RW.A67X.01     2  0.1732      0.748 0.00 0.92 0.00 0.00 0.08
#&gt; TCGA.SP.A6QH.01     1  0.0609      0.957 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.QR.A706.01     1  0.0000      0.959 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     5  0.2616      0.000 0.00 0.10 0.02 0.00 0.88
#&gt; TCGA.S7.A7WV.01     1  0.0609      0.957 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.S7.A7WQ.01     2  0.4854      0.604 0.00 0.68 0.00 0.06 0.26
#&gt; TCGA.S7.A7X0.01     1  0.1216      0.956 0.96 0.00 0.02 0.02 0.00
#&gt; TCGA.TT.A6YK.01     4  0.2873      0.000 0.00 0.12 0.00 0.86 0.02
#&gt; TCGA.QR.A70N.01     2  0.5232      0.399 0.00 0.60 0.00 0.06 0.34
#&gt; TCGA.QR.A70J.01     1  0.0000      0.959 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     3  0.0000      0.000 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A6H5.01     1  0.2249      0.927 0.92 0.00 0.04 0.02 0.02
#&gt; TCGA.P8.A5KC.01     2  0.3731      0.665 0.00 0.80 0.00 0.16 0.04
#&gt; TCGA.QT.A5XL.01     2  0.3390      0.718 0.00 0.84 0.00 0.06 0.10
</code></pre>

<script>
$('#tab-node-041-get-classes-4-a').parent().next().next().hide();
$('#tab-node-041-get-classes-4-a').click(function(){
  $('#tab-node-041-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-041-get-classes-5'>
<p><a id='tab-node-041-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.S7.A7X1.01     2  0.5569      0.543 0.00 0.62 0.00 0.04 0.10 0.24
#&gt; TCGA.RW.A68C.01     2  0.4495      0.643 0.00 0.72 0.00 0.06 0.02 0.20
#&gt; TCGA.TT.A6YP.01     1  0.3007      0.861 0.86 0.00 0.04 0.00 0.02 0.08
#&gt; TCGA.RW.A67X.01     2  0.1092      0.679 0.00 0.96 0.00 0.02 0.02 0.00
#&gt; TCGA.SP.A6QH.01     1  0.0547      0.908 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.QR.A706.01     1  0.2882      0.875 0.86 0.00 0.02 0.00 0.02 0.10
#&gt; TCGA.QR.A6GZ.05     5  0.1092      0.000 0.00 0.02 0.02 0.00 0.96 0.00
#&gt; TCGA.S7.A7WV.01     1  0.0937      0.906 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.S7.A7WQ.01     2  0.4926      0.557 0.00 0.64 0.00 0.00 0.12 0.24
#&gt; TCGA.S7.A7X0.01     1  0.2581      0.886 0.86 0.00 0.00 0.00 0.02 0.12
#&gt; TCGA.TT.A6YK.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.QR.A70N.01     2  0.6228      0.309 0.00 0.44 0.00 0.02 0.18 0.36
#&gt; TCGA.QR.A70J.01     1  0.0000      0.905 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     3  0.0000      0.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6H5.01     1  0.3045      0.827 0.84 0.00 0.10 0.00 0.00 0.06
#&gt; TCGA.P8.A5KC.01     2  0.4222      0.609 0.00 0.70 0.00 0.02 0.02 0.26
#&gt; TCGA.QT.A5XL.01     2  0.2793      0.642 0.00 0.80 0.00 0.00 0.00 0.20
</code></pre>

<script>
$('#tab-node-041-get-classes-5-a').parent().next().next().hide();
$('#tab-node-041-get-classes-5-a').click(function(){
  $('#tab-node-041-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-041-get-classes-6'>
<p><a id='tab-node-041-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.S7.A7X1.01     2  0.4569     0.3183 0.00 0.70 0.00 0.00 0.08 0.18 0.04
#&gt; TCGA.RW.A68C.01     2  0.2376     0.4514 0.00 0.86 0.00 0.00 0.02 0.12 0.00
#&gt; TCGA.TT.A6YP.01     1  0.4070     0.6908 0.62 0.00 0.04 0.00 0.00 0.34 0.00
#&gt; TCGA.RW.A67X.01     2  0.3908     0.2580 0.00 0.72 0.00 0.00 0.00 0.08 0.20
#&gt; TCGA.SP.A6QH.01     1  0.0863     0.8246 0.96 0.00 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.QR.A706.01     1  0.1363     0.8102 0.94 0.00 0.00 0.00 0.00 0.04 0.02
#&gt; TCGA.QR.A6GZ.05     5  0.0504     0.0000 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.S7.A7WV.01     1  0.0504     0.8229 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.S7.A7WQ.01     7  0.6450     0.0476 0.00 0.32 0.00 0.00 0.08 0.20 0.40
#&gt; TCGA.S7.A7X0.01     1  0.1664     0.8000 0.92 0.00 0.00 0.00 0.00 0.06 0.02
#&gt; TCGA.TT.A6YK.01     4  0.0000     0.0000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.QR.A70N.01     7  0.3991     0.2164 0.00 0.22 0.00 0.02 0.04 0.00 0.72
#&gt; TCGA.QR.A70J.01     1  0.2422     0.8000 0.82 0.00 0.00 0.00 0.00 0.18 0.00
#&gt; TCGA.W2.A7UY.01     3  0.0000     0.0000 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6H5.01     1  0.4638     0.6161 0.54 0.00 0.08 0.00 0.00 0.38 0.00
#&gt; TCGA.P8.A5KC.01     2  0.4872     0.3923 0.00 0.60 0.00 0.00 0.02 0.30 0.08
#&gt; TCGA.QT.A5XL.01     2  0.5047     0.2445 0.00 0.52 0.00 0.00 0.00 0.14 0.34
</code></pre>

<script>
$('#tab-node-041-get-classes-6-a').parent().next().next().hide();
$('#tab-node-041-get-classes-6-a').click(function(){
  $('#tab-node-041-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-041-get-classes-7'>
<p><a id='tab-node-041-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6   p7   p8
#&gt; TCGA.S7.A7X1.01     2  0.5104      0.291 0.00 0.66  0 0.04 0.04 0.14 0.12 0.00
#&gt; TCGA.RW.A68C.01     2  0.0471      0.435 0.00 0.98  0 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.TT.A6YP.01     1  0.3299      0.513 0.56 0.00  0 0.44 0.00 0.00 0.00 0.00
#&gt; TCGA.RW.A67X.01     2  0.3975      0.161 0.00 0.66  0 0.00 0.00 0.08 0.26 0.00
#&gt; TCGA.SP.A6QH.01     1  0.1563      0.749 0.90 0.00  0 0.10 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A706.01     1  0.2267      0.698 0.82 0.00  0 0.18 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6GZ.05     5  0.0000      0.000 0.00 0.00  0 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WV.01     1  0.1765      0.748 0.88 0.00  0 0.12 0.00 0.00 0.00 0.00
#&gt; TCGA.S7.A7WQ.01     7  0.6088      0.275 0.00 0.18  0 0.10 0.02 0.18 0.52 0.00
#&gt; TCGA.S7.A7X0.01     1  0.2534      0.683 0.78 0.00  0 0.22 0.00 0.00 0.00 0.00
#&gt; TCGA.TT.A6YK.01     8  0.0000      0.000 0.00 0.00  0 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.QR.A70N.01     6  0.1741      0.000 0.00 0.02  0 0.00 0.04 0.92 0.02 0.00
#&gt; TCGA.QR.A70J.01     1  0.0471      0.756 0.98 0.00  0 0.02 0.00 0.00 0.00 0.00
#&gt; TCGA.W2.A7UY.01     3  0.0000      0.000 0.00 0.00  1 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.QR.A6H5.01     1  0.3272      0.552 0.58 0.00  0 0.42 0.00 0.00 0.00 0.00
#&gt; TCGA.P8.A5KC.01     2  0.6043      0.085 0.00 0.48  0 0.06 0.00 0.06 0.32 0.08
#&gt; TCGA.QT.A5XL.01     7  0.2981      0.177 0.00 0.22  0 0.00 0.00 0.02 0.76 0.00
</code></pre>

<script>
$('#tab-node-041-get-classes-7-a').parent().next().next().hide();
$('#tab-node-041-get-classes-7-a').click(function(){
  $('#tab-node-041-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-041-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-041-consensus-heatmap'>
<ul>
<li><a href='#tab-node-041-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-041-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-041-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-041-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-041-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-041-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-041-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-041-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-041-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-041-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-041-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-041-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-041-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-041-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-041-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-041-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-041-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-041-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-041-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-041-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-041-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-041-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-041-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-041-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-041-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-041-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-041-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-041-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-041-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-041-membership-heatmap'>
<ul>
<li><a href='#tab-node-041-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-041-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-041-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-041-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-041-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-041-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-041-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-041-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-041-membership-heatmap-1-1.png" alt="plot of chunk tab-node-041-membership-heatmap-1"/></p>

</div>
<div id='tab-node-041-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-041-membership-heatmap-2-1.png" alt="plot of chunk tab-node-041-membership-heatmap-2"/></p>

</div>
<div id='tab-node-041-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-041-membership-heatmap-3-1.png" alt="plot of chunk tab-node-041-membership-heatmap-3"/></p>

</div>
<div id='tab-node-041-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-041-membership-heatmap-4-1.png" alt="plot of chunk tab-node-041-membership-heatmap-4"/></p>

</div>
<div id='tab-node-041-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-041-membership-heatmap-5-1.png" alt="plot of chunk tab-node-041-membership-heatmap-5"/></p>

</div>
<div id='tab-node-041-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-041-membership-heatmap-6-1.png" alt="plot of chunk tab-node-041-membership-heatmap-6"/></p>

</div>
<div id='tab-node-041-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-041-membership-heatmap-7-1.png" alt="plot of chunk tab-node-041-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-041-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-041-get-signatures'>
<ul>
<li><a href='#tab-node-041-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-041-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-041-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-041-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-041-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-041-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-041-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-041-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-041-get-signatures-1-1.png" alt="plot of chunk tab-node-041-get-signatures-1"/></p>

</div>
<div id='tab-node-041-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-041-get-signatures-2-1.png" alt="plot of chunk tab-node-041-get-signatures-2"/></p>

</div>
<div id='tab-node-041-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-041-get-signatures-3-1.png" alt="plot of chunk tab-node-041-get-signatures-3"/></p>

</div>
<div id='tab-node-041-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-041-get-signatures-4-1.png" alt="plot of chunk tab-node-041-get-signatures-4"/></p>

</div>
<div id='tab-node-041-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-041-get-signatures-5-1.png" alt="plot of chunk tab-node-041-get-signatures-5"/></p>

</div>
<div id='tab-node-041-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-041-get-signatures-6-1.png" alt="plot of chunk tab-node-041-get-signatures-6"/></p>

</div>
<div id='tab-node-041-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-041-get-signatures-7-1.png" alt="plot of chunk tab-node-041-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-041-signature_compare](figure_cola/node-041-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-041-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-041-dimension-reduction'>
<ul>
<li><a href='#tab-node-041-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-041-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-041-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-041-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-041-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-041-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-041-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-041-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-041-dimension-reduction-1-1.png" alt="plot of chunk tab-node-041-dimension-reduction-1"/></p>

</div>
<div id='tab-node-041-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-041-dimension-reduction-2-1.png" alt="plot of chunk tab-node-041-dimension-reduction-2"/></p>

</div>
<div id='tab-node-041-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-041-dimension-reduction-3-1.png" alt="plot of chunk tab-node-041-dimension-reduction-3"/></p>

</div>
<div id='tab-node-041-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-041-dimension-reduction-4-1.png" alt="plot of chunk tab-node-041-dimension-reduction-4"/></p>

</div>
<div id='tab-node-041-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-041-dimension-reduction-5-1.png" alt="plot of chunk tab-node-041-dimension-reduction-5"/></p>

</div>
<div id='tab-node-041-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-041-dimension-reduction-6-1.png" alt="plot of chunk tab-node-041-dimension-reduction-6"/></p>

</div>
<div id='tab-node-041-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-041-dimension-reduction-7-1.png" alt="plot of chunk tab-node-041-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-041-collect-classes](figure_cola/node-041-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

## Session info


```r
sessionInfo()
```

```
#> R version 4.1.0 (2021-05-18)
#> Platform: x86_64-pc-linux-gnu (64-bit)
#> Running under: CentOS Linux 7 (Core)
#> 
#> Matrix products: default
#> BLAS/LAPACK: /usr/lib64/libopenblas-r0.3.3.so
#> 
#> locale:
#>  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C               LC_TIME=en_US.UTF-8       
#>  [4] LC_COLLATE=en_US.UTF-8     LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
#>  [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                  LC_ADDRESS=C              
#> [10] LC_TELEPHONE=C             LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       
#> 
#> attached base packages:
#> [1] grid      stats     graphics  grDevices utils     datasets  methods   base     
#> 
#> other attached packages:
#> [1] genefilter_1.74.0    ComplexHeatmap_2.8.0 markdown_1.1         knitr_1.33          
#> [5] matrixStats_0.59.0   cola_1.9.4          
#> 
#> loaded via a namespace (and not attached):
#>   [1] bitops_1.0-7           bit64_4.0.5            doParallel_1.0.16      RColorBrewer_1.1-2    
#>   [5] httr_1.4.2             GenomeInfoDb_1.28.1    data.tree_1.0.0        tools_4.1.0           
#>   [9] utf8_1.2.1             R6_2.5.0               irlba_2.3.3            DBI_1.1.1             
#>  [13] BiocGenerics_0.38.0    colorspace_2.0-2       GetoptLong_1.0.5       gridExtra_2.3         
#>  [17] tidyselect_1.1.1       bit_4.0.4              compiler_4.1.0         Biobase_2.52.0        
#>  [21] Cairo_1.5-12.2         xml2_1.3.2             microbenchmark_1.4-7   slam_0.1-48           
#>  [25] scales_1.1.1           askpass_1.1            stringr_1.4.0          digest_0.6.27         
#>  [29] XVector_0.32.0         pkgconfig_2.0.3        umap_0.2.7.0           fastmap_1.1.0         
#>  [33] highr_0.9              rlang_0.4.11           GlobalOptions_0.1.2    rstudioapi_0.13       
#>  [37] RSQLite_2.2.7          impute_1.66.0          generics_0.1.0         shape_1.4.6           
#>  [41] jsonlite_1.7.2         mclust_5.4.7           dplyr_1.0.7            dendextend_1.15.1     
#>  [45] RCurl_1.98-1.3         magrittr_2.0.1         GenomeInfoDbData_1.2.6 Matrix_1.3-4          
#>  [49] fansi_0.5.0            Rcpp_1.0.7             munsell_0.5.0          S4Vectors_0.30.0      
#>  [53] viridis_0.6.1          reticulate_1.20        lifecycle_1.0.0        scatterplot3d_0.3-41  
#>  [57] stringi_1.7.3          zlibbioc_1.38.0        blob_1.2.1             parallel_4.1.0        
#>  [61] crayon_1.4.1           lattice_0.20-44        Biostrings_2.60.1      splines_4.1.0         
#>  [65] annotate_1.70.0        circlize_0.4.13        KEGGREST_1.32.0        polylabelr_0.2.0      
#>  [69] pillar_1.6.1           rjson_0.2.20           codetools_0.2-18       stats4_4.1.0          
#>  [73] XML_3.99-0.6           glue_1.4.2             evaluate_0.14          png_0.1-7             
#>  [77] vctrs_0.3.8            foreach_1.5.1          polyclip_1.10-0        purrr_0.3.4           
#>  [81] gtable_0.3.0           openssl_1.4.4          assertthat_0.2.1       clue_0.3-59           
#>  [85] cachem_1.0.5           ggplot2_3.3.5          xfun_0.24              eulerr_6.1.0          
#>  [89] xtable_1.8-4           skmeans_0.2-13         RSpectra_0.16-0        viridisLite_0.4.0     
#>  [93] survival_3.2-11        tibble_3.1.2           Polychrome_1.3.1       iterators_1.0.13      
#>  [97] AnnotationDbi_1.54.1   memoise_2.0.0          IRanges_2.26.0         cluster_2.1.2         
#> [101] ellipsis_0.3.2         brew_1.0-6
```




