---
layout: post
title: Covering Oregon
date: 2016-01-30 23:15:07.000000000 -05:00
type: post
published: true
status: publish
categories: []
tags: []
meta:
  _thumbnail_id: '1399'
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
  _publicize_job_id: '19297145525'
author:
  login: openelections
  email: openelections@gmail.com
  display_name: openelections
  first_name: ''
  last_name: ''
---
We've spent a lot of time in Oregon. Well, not __in__ Oregon, physically, but searching for, obtaining and parsing election results from the state. County-level data is easy to find: the Secretary of State's office provides [electronic PDFs of results](http://sos.oregon.gov/elections/Pages/electionhistory.aspx) for elections dating back to 2004. Thanks to Tabula, those were easy to convert so that we could load them into our database.

![Map]({{ site.baseurl }}/assets/images/map.png "map")
##### Source: http://www.oregon.gov/DHS/CHILDREN/FOSTERPARENT/PublishingImages/map.png

But precinct-level data was, as we've said before, a whole other story. We've written about specific aspects of this process, but here is the complete story about how we published what is, to the best of our knowledge, the first freely-available set of statewide precinct-level election results for 2012 and 2014 elections in Oregon.

We began gathering Oregon data in [early May 2015](https://github.com/openelections/openelections-data-or/commit/0685040880a9120dc2f119c35168416679522b2b), starting with the county-level data and then moving onto individual counties. We asked about other sources of precinct-level data, but never found a freely available one. The state does not maintain precinct-level results data. When we turned to the counties, we found a few that provided machine-readable results (mostly in PDF format), including the largest counties (Multnomah, Clackamas and Marion among them). Parsing those results was by no means [simple](https://github.com/openelections/openelections-data-or/blob/master/multnomah_parser.py), but the files were consistent enough to allow us to grab precinct results.
But for the bulk of Oregon's 36 counties, here was our process:

  1. Email county clerk's office asking about the availability of results. Sometimes we called.
  2. Request results for 2000-2014, if available. If not, request as much as they had.
  3. For some, pay a fee for the results, ranging from $37.50 (Union County) to $222.75 (Tillamook County, just for 2010-2014).
  4. Get the results, typically PDF image files that would require OCR to convert into machine-readable data. In some cases, we were sent paper via the postal service.
  5. Create election and county-specific files.

We had several volunteers (some listed [here](https://github.com/openelections/openelections-data-or/network/members)) help us with the conversion process, which helped us get the data converted faster. All told, we spent more than $1,000 on Oregon precinct-level results, and for that we got a wide range of files covering most of the elections we sought but not all.

We built a [matrix](https://github.com/openelections/openelections-data-or/blob/master/county_matrix.csv) showing the county coverage that we have, something that we'll be doing for other states and putting on openelections.net as well. In many counties, getting pre-2008 results was either impossible or cost-prohibitive. In one case, Crook County, the precinct results from the 2010 general and 2012 primary elections are no longer available. To repeat: no government entity has precinct-level results for Crook County for those two elections. They are missing from the public record.

Almost every county clerk we spoke or emailed with was friendly and wanted to help us. Many offered results for free online, and we happily downloaded those files. Others had results but have not posted them. Many of them appear to use the same software to produce election results reports but continue to print out those electronic reports and scan them, reducing legibility.

Oregon is, sadly, not an isolated case. There are other states where obtaining precinct-level results is a painstaking effort, even when counties and states produce electronic version of political maps and voter files. Election results, in too many cases, are a weak link in our civic infrastructure.

So we'll be back in touch with our Oregon clerks at the end of this year or early next year, asking for more election results. We'll know what to expect this time, and it should be a less-expensive and shorter process. But on both counts, the progress isn't enough.
