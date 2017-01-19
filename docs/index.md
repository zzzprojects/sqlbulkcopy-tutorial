---
layout: post
---

<html lang="en">
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
		<meta http-equiv="x-ua-compatible" content="ie=edge">
		<meta name="msvalidate.01" content="89359D9C492A475C0061398008D105FB" />
		
		<!-- seo !-->
		<meta name="description" content="Extend and Overcome Entity Framework Limitations with Must-Have Features">
		<meta name="keywords" content="BulkSaveChanges, BulkInsert, BulkUpdate, BulkDelete, BulkMerge, Query Cache, Query Filter, Query Future, Query IncludeFilter, Audit">
		<title>EF Must-Have Features | Bulk Operations | Batch Delete | Batch Update | Query Cache | Query Filter | Query Future | Query Include | Audit</title>
		
		<!-- icon/css !-->
		<link rel="icon" type="image/png" href="http://entityframework-plus.net/images/logo.png">
		<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.2/css/bootstrap.min.css" integrity="sha384-y3tfxAZXuh4HwSYylfB+J125MxIs6mR5FOHamPBG064zB+AFeWH94NdvaCBm8qnd" crossorigin="anonymous">
		<link rel="stylesheet" type="text/css" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
		<link rel="stylesheet" type="text/css" href="http://entityframework-plus.net/css/github2.css">
		<link rel="stylesheet" type="text/css" href="http://entityframework-plus.net/css/default.1.3.css">
	</head>
	
	<body>
		
		<!-- top-navbar !-->
		<nav id="top-navbar" class="navbar hidden-md-down">
			<div class="container-fluid">
			
				<!-- navbar-nav-product !-->
				<ul class="nav navbar-nav navbar-nav-product">
					<li class="nav-item">
						<a href="#" class="nav-link navbar-toggler collapsed" type="button" data-toggle="collapse" data-target="#top-product"><img src="http://entityframework-plus.net/images/logo.png" height="40" />&nbsp;Products&nbsp;<i class="fa fa-caret-down" aria-hidden="true"></i><i class="fa fa-caret-up" aria-hidden="true"></i></a>
					</li>
				</ul>
				
				<!-- navbar-nav-share !-->				
				<ul class="nav navbar-nav pull-xs-right navbar-nav-share">
					<li class="nav-item">
						<a href="mailto:info@zzzprojects.com"><i class="fa fa-envelope"></i>&nbsp;&nbsp;info@zzzprojects.com</a>
					</li>
					<li class="nav-item">
						<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
					</li>
					<li class="nav-item">
						<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
					</li>
					<li class="nav-item">
						<a href="https://plus.google.com/+Zzzprojects_NetSQL" target="_blank"><i class="fa fa-google-plus"></i></a>
					</li>				
					<li class="nav-item">
						<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank" class="hidden-xs-down"><i class="fa fa-newspaper-o"></i></a>
					</li>
				</ul>
				
			</div>
		</nav>
		
		<!-- top-product !-->
		<div id="top-product" class="collapse hidden-md-down">
			<div class="container">
				<div class="row">
					<div class="col-lg-3">
						<h3>Entity Framework</h3>
						<ul>
							<li><a href="http://entityframework-extensions.net/" target="_blank">Entity Framework Extensions</a></li>
							<li><a href="http://entityframework-plus.net/" target="_blank">Entity Framework Plus (EF+)</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Bulk Operations</h3>
						<ul>
							<li><a href="http://bulk-operations.net/" target="_blank">Bulk Operations</a></li>
							<li><a href="http://dapper-plus.net/" target="_blank">Dapper Plus</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Expression Evaluator</h3>
						<ul>
							<li><a href="http://eval-expression.net/" target="_blank">Eval Expression.NET</a></li>
							<li><a href="http://eval-sql.net/" target="_blank">Eval SQL.NET</a></li>								
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Others</h3>
						<ul>
							<li><a href="https://github.com/zzzprojects/Z.ExtensionMethods" target="_blank">Extension Methods</a></li>
							<li><a href="https://github.com/zzzprojects/LINQ-Async" target="_blank">LINQ Async</a></li>
						</ul>
					</div>
				</div>
			</div>	
		</div>

		<!-- menu !-->
		<nav id="menu" class="navbar">
			<div class="container">
				<div class="row">
					<div class="col-xs-10 col-lg-12">
						<!-- navbar-bar-header !-->
						<ul class="nav navbar-nav navbar-nav-header">
							<li class="nav-item">
								<h1>Entity Framework Plus
								<small>EF Must-Have Features</small>
								</h1>
							</li>
						</ul>
						
						<!-- navbar-bar-menu !-->
						<ul class="nav navbar-nav pull-xs-right navbar-nav-menu hidden-md-down">
							<li class="nav-item">
								<a class="nav-link" href="https://github.com/zzzprojects/EntityFramework-Plus/wiki" target="_blank">Wiki</a>
							</li>
							<li class="nav-item">
								<a class="nav-link" href="https://github.com/zzzprojects/EntityFramework-Plus/issues" target="_blank">Forum</a>
							</li>
							<li class="nav-item">
								<a class="nav-link" href="https://github.com/zzzprojects/EntityFramework-Plus" target="_blank">Source Code</a>
							</li>						
							
							<li class="nav-item">
								<a href="https://github.com/zzzprojects/EntityFramework-Plus/wiki/Downloads" target="_blank" class="btn btn-success" role="button" onclick="ga('send', 'event', { eventAction: 'download'});"><span><i class="fa fa-cloud-download"></i>&nbsp;<span>Download</span></span></a>
							</li>
						</ul>
					</div>
					
					<div class="col-xs-2">
						<!-- navbar-bar-menu-mobile !-->
						<ul class="nav navbar-nav pull-xs-right hidden-lg-up navbar-bar-menu-mobile">
							<li class="nav-item">
								<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#menu-mobile">&#9776;</button>
							</li>
						</ul>
					</div>
				</div>
			</div>
		</nav>
		
		<div id="menu-mobile" class="collapse hidden-lg-up">
			<div class="container">
				<br />
				<div class="row">
					<div class="col-lg-3">			
						<h3>Menu</h3>
						<ul>
							<li><a class="nav-link" href="https://github.com/zzzprojects/EntityFramework-Plus/wiki" target="_blank">Wiki</a></li>
							<li><a class="nav-link" href="https://github.com/zzzprojects/EntityFramework-Plus/issues" target="_blank">Forum</a></li>
							<li><a class="nav-link" href="#pro">PRO Version</a></li>
							<li><a href="https://github.com/zzzprojects/EntityFramework-Plus/wiki/Downloads" target="_blank" class="btn btn-success" role="button" onclick="ga('send', 'event', { eventAction: 'download'});"><span><i class="fa fa-cloud-download"></i>&nbsp;<span>Download</span></span></a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Entity Framework</h3>
						<ul>
							<li><a href="http://entityframework-extensions.net/" target="_blank">Entity Framework Extensions</a></li>
							<li><a href="http://entityframework-plus.net/" target="_blank">Entity Framework Plus (EF+)</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Bulk Operations</h3>
						<ul>
							<li><a href="http://bulk-operations.net/" target="_blank">Bulk Operations</a></li>
							<li><a href="http://dapper-plus.net/" target="_blank">Dapper Plus</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Expression Evaluator</h3>
						<ul>
							<li><a href="http://eval-expression.net/" target="_blank">Eval Expression.NET</a></li>
							<li><a href="http://eval-sql.net/" target="_blank">Eval SQL.NET</a></li>								
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Others</h3>
						<ul>
							<li><a href="https://github.com/zzzprojects/Z.ExtensionMethods" target="_blank">Extension Methods</a></li>
							<li><a href="https://github.com/zzzprojects/LINQ-Async" target="_blank">LINQ Async</a></li>
						</ul>
					</div>
				</div>
			</div>
		</div>
		
		<!-- header !-->
		<header>
			<div class="container">
				<div class="row">
					<div class="col-lg-6">
						<div class="card">
							<div class="card-block">
								<hr class="m-y-md" />
								<h2>Extend and Overcome Entity Framework Limitations with Must-Have Features</h2>
								<hr class="m-y-md" />
								<div class="lead">
									<p>100% Free and Open Source</p>
									<a href="https://github.com/zzzprojects/EntityFramework-Plus/wiki/Downloads" target="_blank" class="btn btn-success btn-lg btn-left" role="button" onclick="ga('send', 'event', { eventAction: 'download'});"><span><i class="fa fa-cloud-download fa-2x"></i>&nbsp;<span>Download</span></span></a><br />	
									<div class="text-muted">Support EF Core, EF6, and EF5</div>
								</div>
							</div>
						</div>
					</div>
					<div class="col-lg-4 col-lg-push-2">
						<div class="card">
							<h2>Main Features</h2>
							<ul style="font-size: 18px;">
								<li>Auditing</li>
								<li>Batch Delete</li>
								<li>Batch Update</li>
								<li>LINQ Dynamic</li>
								<li>Query Cache</li>
								<li>Query Deferred</li>
								<li>Query Filter</li>
								<li>Query Future</li>
								<li>Query IncludeFilter</li>
								<li>Query IncludeOptimized</li>
							</ul>
						</div>
					</div>
				</div>
			</div>
		</header>
		
		<!-- featured !-->
		<div id="featured">
			<div class="container">
			
				
			</div>
		</div>
		
		<!-- features !-->
		<div id="feature">
			<div class="container">
				
				<!-- Auditing !-->
				<a id="auditing" href="#"></a>
				<h2>Auditing</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Improve <span class="text-bold-red">security</span> and know what, when and who did a changes in the context.</p>
						<ul>
							<li>AutoSave audit values in the database</li>
							<li>Keep track of SoftDelete entities</li>
							<li>Filter events you desire</li>
							<li>Include entity type you desire</li>
							<li>Format value in your specific format</li>
						</ul>
						
					</div>
					<div class="col-lg-7">
{% highlight csharp %}
var audit = new Audit();
audit.CreatedBy = "ZZZ Projects"; // Optional
ctx.SaveChanges(audit);

// Access to all auditing information
var entries = audit.Entries;
foreach(var entry in entries)
{
    foreach(var property in entry.Properties)
    {
    }
}
{% endhighlight %}	
					</div>
				</div>
								
				<hr class="m-y-md" />
				
				<!-- Delete without loading entities !-->
				<a id="delete-without-loading-entities" href="#"></a>
				<h2>Delete without loading entities</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Delete rows from LINQ Query in a single database round trip without loading entities in the context</p>
						<ul>
							<li>Use Async methods to make your application responsive</li>
							<li>Use batch size to improve performance</li>
							<li>Use batch delay interval to reduce server load</li>
							<li>Use Intercept to customize DbCommand</li>
						</ul>
						
					</div>
					<div class="col-lg-7">
{% highlight csharp %}
// DELETE all users inactive for 2 years
ctx.Users.Where(x => x.LastLoginDate < DateTime.Now.AddYears(-2))
         .Delete();

// DELETE using a BatchSize
ctx.Users.Where(x => x.LastLoginDate < DateTime.Now.AddYears(-2))
         .Delete(x => x.BatchSize = 1000);
{% endhighlight %}	
					</div>
				</div>
								
				<hr class="m-y-md" />
				
				<!-- Update without loading entities !-->
				<a id="update-without-loading-entities" href="#"></a>
				<h2>Update without loading entities</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Update rows from LINQ Query in a single database round trip without loading entities in the context</p>
						<ul>
							<li>Use Async methods to make your application responsive</li>
							<li>Use Intercept to customize DbCommand</li>
						</ul>
						
					</div>
					<div class="col-lg-7">
{% highlight csharp %}
// UPDATE all users inactive for 2 years
ctx.Users.Where(x => x.LastLoginDate < DateTime.Now.AddYears(-2))
         .Update(x => new User() { IsSoftDeleted = 1 });
{% endhighlight %}	
					</div>
				</div>
								
				<hr class="m-y-md" />

				<!-- Second Level Cache !-->
				<a id="second-level-cache" href="#"></a>
				<h2>Second Level Cache</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Improve application <span class="text-bold-red">performance</span> and reduce sql server load by using a second level caching.</p>
						<ul>
							<li>Use Cache Tag to expire cache</li>
							<li>Use Cache Policy to control caching</li>
						</ul>
						
					</div>
					<div class="col-lg-7">
{% highlight csharp %}
// The first call perform a database round trip
var countries1 = ctx.Countries.FromCache().ToList();

// Subsequent calls will take the value from the memory instead
var countries2 = ctx.Countries.FromCache().ToList();
{% endhighlight %}	
					</div>
				</div>
								
				<hr class="m-y-md" />
				
				<!-- Filtering !-->
				<a id="filtering" href="#"></a>
				<h2>Filtering</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Improve your context <span class="text-bold-red">extensibility</span> and create filters to query only what's really available.</p>
						<ul>
							<li>Create Multi-Tenancy application</li>
							<li>Exclude soft deleted record</li>
							<li>Filter record by security access</li>
						</ul>
						
					</div>
					<div class="col-lg-7">
{% highlight csharp %}
QueryFilterManager.Filter<Post>(q => q.Where(x => !x.IsSoftDeleted));

var ctx = new EntitiesContext();

// SELECT * FROM Post WHERE IsSoftDeleted = false
var list = ctx.Posts.ToList();
{% endhighlight %}	
					</div>
				</div>
								
				<hr class="m-y-md" />
				
				<!-- Future & FutureValue !-->
				<a id="future--futurevalue" href="#"></a>
				<h2>Future & FutureValue</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Delay queries execution and batch all queries in a single database round trip.</p>
						<ul>
							<li>Query Future</li>
							<li>Query Future Value</li>
							<li>Query Future Value Deferred</li>
							<li>Include entity type you desire</li>
							<li>Format value in your specific format</li>
						</ul>
						
					</div>
					<div class="col-lg-7">
{% highlight csharp %}
// CREATE a pending list of future queries
var futureCountries = db.Countries.Where(x => x.IsActive).Future();
var futureStates = db.States.Where(x => x.IsActive).Future();

// TRIGGER all pending queries in one database round trip
// SELECT * FROM Country WHERE IsActive = true;
// SELECT * FROM State WHERE IsActive = true
var countries = futureCountries.ToList();

// futureStates is already resolved and contains the result
var states = futureStates.ToList();
{% endhighlight %}	
					</div>
				</div>
				
				<hr class="m-y-md" />
				
				<!-- Filter included related entities !-->
				<a id="filter-included-related-entities" href="#"></a>
				<h2>Filter included related entities</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Overcome Include method limitations by filtering included related entities.</p>
						<ul>
							<li>Filter child entities with IncludeFilter</li>
							<li>Improve performance with IncludeOptimized </li>
						</ul>						
					</div>
					<div class="col-lg-7">
{% highlight csharp %}
// LOAD orders and the first 10 active related entities.
var list = ctx.Orders.IncludeFilter(x => x.Items
                                          .Where(y => !y.IsSoftDeleted)
                                          .OrderBy(y => y.Date)
                                          .Take(10))
                     .ToList();
{% endhighlight %}	
					</div>
				</div>
				
				<!-- more-feature !-->
				<p class="more-feature"><a href="https://github.com/zzzprojects/EntityFramework-Plus/wiki" target="_blank" class="btn btn-primary btn-lg" role="button"><span><i class="fa fa-book"></i>&nbsp;<span>View More Features</span></span></a></p>
				
			</div>
		</div>
		
		<!-- support !-->
		<a id="supports" href="#"></a>
		<div id="support">
			<div class="container">
				<h2>Test our <span class="text-bold-red">Outstanding</span> Support</h2>
				<h3>We usually answer within the next business day, hour, or minutes!</h3>
				<div class="row">
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Contact Us</h4>
							</div>
							<a href="mailto:info@zzzprojects.com"><i class="fa fa-users fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Email our team for any questions. We love to hear from you!</p>
								<a href="mailto:info@zzzprojects.com">info@zzzprojects.com</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Wiki</h4>
							</div>
							<a href="https://github.com/zzzprojects/EntityFramework-Plus/wiki" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});"><i class="fa fa-folder-open fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Consult our complete documentation to help you getting started.</p>
								<a href="https://github.com/zzzprojects/EntityFramework-Plus/wiki" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});">Wiki</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Forum</h4>
							</div>
							<a href="https://github.com/zzzprojects/EntityFramework-Plus/issues" target="_blank" onclick="ga('send', 'event', { eventAction: 'forum'});"><i class="fa fa-weixin fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Visit the forum to report issues, ask questions, and propose new features.</p>
								<a href="https://github.com/zzzprojects/EntityFramework-Plus/issues" target="_blank" onclick="ga('send', 'event', { eventAction: 'forum'});">Forum</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Open Source</h4>
							</div>
							<a href="https://github.com/zzzprojects/EntityFramework-Plus" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});"><i class="fa fa-github fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Access the source of the library you're using to understand better its logic.</p>
								<a href="https://github.com/zzzprojects/EntityFramework-Plus" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});">GitHub</a>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
		
		<!-- pricing !-->
		<a id="pro" href="#"></a>
		<div id="pricing">
			<div class="container">
				<div class="row">
					<div class="col-lg-6">
						<h2>Pricing? 100% Free and Open Source</h2>
						<hr class="m-y-md" />
						<p>Entity Framework Plus is 100% free and open source.</p>
						<div>
							<a href="https://github.com/zzzprojects/EntityFramework-Plus/wiki/Downloads" target="_blank" class="btn btn-success btn-lg btn-left" role="button" onclick="ga('send', 'event', { eventAction: 'download'});"><span><i class="fa fa-cloud-download fa-2x"></i>&nbsp;<span>Download</span></span></a><br />	
							<div class="text-muted">* Support EF Core, EF6, and EF5</div>
						</div>
						<hr class="m-y-md" />
						<p>Looking for a high-performance enhancement library?</p>
						<ul>
							<li><a href="http://entityframework-extensions.net/" target="_blank">Entity Framework Extensions</a>
								<ul>
									<li>BulkSaveChanges</li>
									<li>BulkInsert</li>
									<li>BulkUpdate</li>
									<li>BulkDelete</li>
									<li>BulkMerge</li>									
								</ul>
							</li>
							<li><a href="http://bulk-operations.net/" target="_blank">Bulk Operations</a></li>
							<li><a href="http://dapper-plus.net/" target="_blank">Dapper Plus</a></li>
						</ul>
					</div>
					<div class="col-lg-6">
						<table class="table table-hover table-bordered">
							<thead class="thead-inverse">
								<tr>
									<th style="text-align:left">Entity Framework Plus</th>
									<th>100% FREE</th>
								</tr>
							</thead>
							<tbody>
								<tr>
									<th>Audit</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Batch Delete</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Batch Update</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Query Cache</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
							    <tr>
									<th>Query Deferred</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Query Filter</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Query Future</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Query IncludeFilter</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Query IncludeOptimized</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Commercial License</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Support & Upgrades</th>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
							</tbody>
						</table>		
					</div>
				</div>
			</div>
			
			<!-- validation !-->
			<div id="error_validation" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="modal_agreement" aria-hidden="true">
				<div class="modal-dialog" role="document">
					<div class="modal-content">
						<div class="modal-header">
							<h4 class="modal-title" id="modal_agreement">License Agreement</h4>
						</div>
						<div class="modal-body bg-danger">
							You must read and agree to the License Agreement.
						</div>
						<div class="modal-footer">
							<button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
						</div>
					</div>
				</div>
			</div>
		</div>

		<!-- other product !-->
		<div id="product">
			<div class="container">
				<div class="row">
					<div class="col-lg-3">
						<h3>Entity Framework</h3>
						<ul>
							<li><a href="http://entityframework-extensions.net/" target="_blank">Entity Framework Extensions</a></li>
							<li><a href="http://entityframework-plus.net/" target="_blank">Entity Framework Plus (EF+)</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Bulk Operations</h3>
						<ul>
							<li><a href="http://bulk-operations.net/" target="_blank">Bulk Operations</a></li>
							<li><a href="http://dapper-plus.net/" target="_blank">Dapper Plus</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Expression Evaluator</h3>
						<ul>
							<li><a href="http://eval-sql.net/" target="_blank">Eval SQL.NET</a></li>
							<li><a href="http://eval-expression.net/" target="_blank">Eval Expression.NET</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Others</h3>
						<ul>
							<li><a href="https://github.com/zzzprojects/Z.ExtensionMethods" target="_blank">Extension Methods</a></li>
							<li><a href="https://github.com/zzzprojects/LINQ-Async" target="_blank">LINQ Async</a></li>
						</ul>
					</div>
				</div>
			</div>		
		</div>
		
		<!-- footer !-->
		<footer>
			<div class="container text-center-md-down">
				<div class="row">
					<div class="col-lg-6">
						Copyright © <a href="http://www.zzzprojects.com/" target="_blank" class="text-bold">ZZZ Projects Inc.</a> 2014 - 2017
						<div class="hidden-lg-up"></div>
						All rights reserved
					</div>
					<hr class="hidden-lg-up" />
					<div class="col-lg-6 text-right-lg-up social">
						<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
						<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
						<a href="https://plus.google.com/+Zzzprojects_NetSQL" target="_blank"><i class="fa fa-google-plus"></i></a>
						<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank"><i class="fa fa-newspaper-o"></i></a>
					</div>
				</div>
			</div>
		</footer>

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
    <script src="http://entityframework-plus.net/js/tether.min.js"></script>
	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.2/js/bootstrap.min.js" integrity="sha384-vZ2WRJMwsjRMW/8U7i6PWi6AlO1L79snBrmgiDpgIWJ82z8eA5lenwvxbMV1PAh7" crossorigin="anonymous"></script>
	<script type="text/javascript">
	  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
	  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
	  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
	  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

	  ga('create', 'UA-55584370-6', 'auto');
	  ga('send', 'pageview');
	</script>
	</body>
</html>
