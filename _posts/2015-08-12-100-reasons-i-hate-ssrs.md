---
layout: post
title: 100 reasons I hate ssrs
date: '2015-08-12T19:01:00.004Z'
author: Tim Abell
tags: 
modified_time: '2016-11-15T11:49:21.321Z'
blogger_id: tag:blogger.com,1999:blog-5082828566240519947.post-875301386032121102
blogger_orig_url: https://timwise.blogspot.com/2015/08/100-reasons-i-hate-ssrs.html
---

A slightly tongue-in cheek hit-list of nasty things and vague hand-waving opinions on what makes microsoft's sql server reporting services (ssrs) such a pig to work with.<br /><br />I don't really know of anything better so this is mostly just pointless ranting; but I'll justify it to myself by saying at least you'll know what you're getting into if you've read this before you start. SSRS seems to be more "death by one thousand paper cuts" than completely broken, so it's not so easy to say "it's shit, shalln't use it" like any good prima-donna developer would. Sorry I mean rock-star (recruiter speak). It also offers a few features that would be pretty hard to code from hand cost-effectively in something like asp.net mvc, such as user editing, multiple export formats, scheduled emails, and some of the ways you can cut-and-shut the data in the reports.<br /><br />I make no apologies for the colourful language, it's a representation of the emotional side of having to use this heap of crap. <br /><br /><br /><ol><li><a href="http://www.allenkinsel.com/archive/2013/01/adventures-in-ssrs">http://www.allenkinsel.com/archive/2013/01/adventures-in-ssrs </a></li><li>doesn't bind to a port like a normal fukcing service</li><ol><li><a href="http://blogs.devhorizon.com/reza/2008/10/20/say-goodbye-to-iis-say-hello-to-httpsys/">http://blogs.devhorizon.com/reza/2008/10/20/say-goodbye-to-iis-say-hello-to-httpsys/</a></li><li><a href="http://www.iis.net/learn/get-started/introduction-to-iis/introduction-to-iis-architecture#Hypertext">http://www.iis.net/learn/get-started/introduction-to-iis/introduction-to-iis-architecture#Hypertext</a></li><li><a href="https://social.technet.microsoft.com/Forums/sqlserver/en-US/f2586aca-78fe-40d6-9bcd-5151bac7136f/role-of-httpsys-in-ssrs-2008-?forum=sqlreportingservices">https://social.technet.microsoft.com/Forums/sqlserver/en-US/f2586aca-78fe-40d6-9bcd-5151bac7136f/role-of-httpsys-in-ssrs-2008-?forum=sqlreportingservices</a></li><li><a href="http://blogs.technet.com/b/andrew/archive/2007/12/04/sql-server-2008-reporting-services-no-longer-depends-on-iis.aspx">http://blogs.technet.com/b/andrew/archive/2007/12/04/sql-server-2008-reporting-services-no-longer-depends-on-iis.aspx</a></li><li>http server api (aka http.sys)</li></ol><ol><ol><li><a href="https://msdn.microsoft.com/en-us/library/aa364510%28VS.85%29.aspx?f=255&amp;MSPPError=-2147217396">https://msdn.microsoft.com/en-us/library/aa364510%28VS.85%29.aspx?f=255&amp;MSPPError=-2147217396</a></li></ol><li>list reservations:</li><ol><li>`netsh http show urlacl`</li></ol></ol><li>auth in reporting <a href="https://msdn.microsoft.com/en-us/library/ms152899.aspx">https://msdn.microsoft.com/en-us/library/ms152899.aspx</a></li><li>reports in VS</li><ol><li><a href="http://curah.microsoft.com/22200/create-ssrs-reports-using-visual-studio">http://curah.microsoft.com/22200/create-ssrs-reports-using-visual-studio</a></li><li><a href="https://msdn.microsoft.com/en-us/library/ms173745.aspx">https://msdn.microsoft.com/en-us/library/ms173745.aspx</a></li></ol><li>"Explicity add new role assingment for the account you are using and check every box in sight" ~ a.n. colleague.&nbsp; lol</li><li>ignore the .rdl.data files with git.</li><ol><li><a href="http://stackoverflow.com/questions/3424928/in-ssrs-is-there-a-way-to-disable-the-rdl-data-file-creation#3425429">http://stackoverflow.com/questions/3424928/in-ssrs-is-there-a-way-to-disable-the-rdl-data-file-creation#3425429</a></li></ol><li>no folders.</li><ol><li><a href="https://connect.microsoft.com/SQLServer/feedback/details/487106/allow-sub-folders-in-ssrs-projects">https://connect.microsoft.com/SQLServer/feedback/details/487106/allow-sub-folders-in-ssrs-projects</a></li><li><a href="http://stackoverflow.com/questions/3309002/visual-studio-for-ssrs-2008-how-to-organize-reports-into-subfolders-in-solutio">http://stackoverflow.com/questions/3309002/visual-studio-for-ssrs-2008-how-to-organize-reports-into-subfolders-in-solutio</a></li></ol><li>renamed a dataset, nothing fucking broke!!!!!!!!!!!!!!!!!!!!!!!!!!! even though there are reports that depend on it. On editing the report's dataset list you can see clearly "not found", but yet it still runs. what in the blazes is that all about?</li><ol><li>caching in the report editor <a href="http://stackoverflow.com/q/3424928/10245">http://stackoverflow.com/q/3424928/10245</a></li><li>kill the .data cache files <a href="http://stackoverflow.com/questions/3424928/in-ssrs-is-there-a-way-to-disable-the-rdl-data-file-creation">http://stackoverflow.com/questions/3424928/in-ssrs-is-there-a-way-to-disable-the-rdl-data-file-creation</a></li><li>git clean -xfd</li><li>fuck</li><li><a href="https://social.msdn.microsoft.com/Forums/sqlserver/en-US/0aa81692-352f-4c1f-a0e3-95fe6c0797ca/cachedataforpreview-in-rsreportdesignerconfig-not-honored">https://social.msdn.microsoft.com/Forums/sqlserver/en-US/0aa81692-352f-4c1f-a0e3-95fe6c0797ca/cachedataforpreview-in-rsreportdesignerconfig-not-honored</a></li><li><a href="https://connect.microsoft.com/SQLServer/feedback/details/468482">https://connect.microsoft.com/SQLServer/feedback/details/468482</a></li><li>it's the `bin\` folder, not the .data files. Still, fuckkkk.</li></ol><li>to get from a report to a db you go, report &gt; report dataset &gt; shared dataset &gt; db, but db is defined in the shared dataset with another name, which can be pointed to a shared data source, which is also named. and *that* data source actually has a connection string</li><li>committing to tfs failed half way through because vs had locked a bunch of files I didn't even have open</li><li>found a param with &lt;Value&gt;=Microsoft.VisualBasic.Strings.Join(Parameters!Stages.Label, ", ")&lt;/Value&gt; - wtf.</li><li>function overload matching warning wouldn't go away till I closed the sln</li><li>localisation is a bitch</li><ol><li><a href="http://stackoverflow.com/questions/10953629/how-to-change-ssrs-2008-locale">http://stackoverflow.com/questions/10953629/how-to-change-ssrs-2008-locale</a> etc</li><li><a href="http://blog.ponytailbob.com/2007/10/multi-language-tips-in-ssrs.html">http://blog.ponytailbob.com/2007/10/multi-language-tips-in-ssrs.html</a></li><li><a href="http://blogs.msdn.com/b/sriram_reddy1/archive/2012/01/09/localization-in-ssrs-reports.aspx">http://blogs.msdn.com/b/sriram_reddy1/archive/2012/01/09/localization-in-ssrs-reports.aspx</a></li><li><a href="https://support.microsoft.com/en-gb/kb/919153">https://support.microsoft.com/en-gb/kb/919153</a></li><li><a href="http://www.keepitsimpleandfast.com/2011/09/localization-of-your-ssrs-reports.html">http://www.keepitsimpleandfast.com/2011/09/localization-of-your-ssrs-reports.html</a></li><li>why you no use User!Language??</li></ol><li>Visual Studio 2013 crashed. hard. while cancelling new report param</li><li>adds 00:00:00 to date fields from sql server. duuuuuuuuuuuuh (goes via .net datetime internally, but even so, not friendly)</li><li>changed date format, looks fine in VS, but no change in report server. wuh? deploy all</li><li>no auto-sizing of cols <a href="http://stackoverflow.com/questions/7851045/ssrs-tablix-column-cangrow-property-for-width">http://stackoverflow.com/questions/7851045/ssrs-tablix-column-cangrow-property-for-width</a></li><li>no nulls in multi-value <a href="http://www.keepitsimpleandfast.com/2012/03/how-to-pass-null-value-to-multi-value.html">http://www.keepitsimpleandfast.com/2012/03/how-to-pass-null-value-to-multi-value.html</a></li><li>need dirty hack to show "all" rather than full list</li><ol><li><a href="http://www.mssqltips.com/sqlservertip/2844/working-with-multiselect-parameters-for-ssrs-reports/">http://www.mssqltips.com/sqlservertip/2844/working-with-multiselect-parameters-for-ssrs-reports/</a></li><li><a href="http://stackoverflow.com/questions/12917261/optional-multi-valued-parameters-in-ssrs">http://stackoverflow.com/questions/12917261/optional-multi-valued-parameters-in-ssrs</a></li><li><a href="http://www.bi-rootdata.com/2012/09/efficient-way-of-using-all-as-parameter.html">http://www.bi-rootdata.com/2012/09/efficient-way-of-using-all-as-parameter.html</a></li><li><a href="http://blog.ponytailbob.com/2007/10/2-shortcomings-of-multi-valued.html">http://blog.ponytailbob.com/2007/10/2-shortcomings-of-multi-valued.html</a></li></ol><li>some fucking horror I've yet to encounter (querystrings) <a href="http://stackoverflow.com/questions/512105/passing-multiple-values-for-a-single-parameter-in-reporting-services">http://stackoverflow.com/questions/512105/passing-multiple-values-for-a-single-parameter-in-reporting-services</a></li><li>it has a fucking canvas size that will push over to 2 pages</li><li>the font kerning on a print is massively different to on web / design view</li><li>sorting</li><ol><li><a href="http://stackoverflow.com/questions/9254604/why-does-my-sql-server-reporting-service-ssrs-report-appear-to-re-sort-the-d">http://stackoverflow.com/questions/9254604/why-does-my-sql-server-reporting-service-ssrs-report-appear-to-re-sort-the-d</a></li></ol><li>"Index was out of range. Must be non-negative and less than the size of the collection. Parameter name: index " from editing xml. thanks for the error info. fuckkkkkers</li><li>the ssrs gui editor is a flaky piece of shit</li><ol><li>doesn't select the right fucking textbox in the props window</li><li>had to restart visual fuckigjn studio</li><li>grrr</li></ol><li>the underlying xml is fucking horrific</li><li>&lt;rd:Selected&gt;true&lt;/rd:Selected&gt; ----- what in the fucking blazes is that doing in there?</li><li>how do you deploy without connecting visual studio to production server? you fucking don't hahahahahaa</li><li>powerhell <a href="https://gist.github.com/timabell/7e3019bd2de802f0b259">https://gist.github.com/timabell/7e3019bd2de802f0b259</a></li><li>ssbi install croaked - h<a href="ttps://support.microsoft.com/en-us/kb/2800050?wa=wsignin1.0">ttps://support.microsoft.com/en-us/kb/2800050?wa=wsignin1.0</a></li><li>[09:44:53] john doe: Tim can I have a .bak file of ReportServer$MSSQL2012TempDB which the stupid software seems to be unable to operate without even though it has Temp in the database name implying it will rebuild itself (at least that's what it implies to me)</li><ol><li>[09:47:48] Tim Abell: (facepalm)</li><li>[09:47:49] Tim Abell: sure</li><li>[09:48:08] Tim Abell: I did wonder, and then I thought, no they couldn't possibly need that</li></ol><li>dropdown doesn't work in firefox</li><li>no debugging <a href="http://stackoverflow.com/a/14068447/10245">http://stackoverflow.com/a/14068447/10245</a></li><li>Warning : The text box ‘appliedFilters’ and the image ‘urLogo’ overlap. Overlapping report items are not supported in all renderers.</li><li>the only options for DRY in reports suck balls <a href="http://www.3pillarglobal.com/insights/tips-tricks-ensure-consistency-sql-server-reporting-services-reports">http://www.3pillarglobal.com/insights/tips-tricks-ensure-consistency-sql-server-reporting-services-reports</a></li><li><a href="http://harmful.cat-v.org/software/xml/">http://harmful.cat-v.org/software/xml/</a> xml is a terrible format anyway</li><li>layout is in inches</li><li>you can change the layout to cm</li><li>it stores different metrics (cm/in) for each element, wtf, pick a unit</li><li>reflowing nicely is impossible</li><li>layout engine is as intelligent as a piece of paper and a pen. x,y is all you get.</li><li><a href="http://www.webapplicationsuk.com/2010/07/word-html-renderer-ndash-the-road-to-hellhellip/">http://www.webapplicationsuk.com/2010/07/word-html-renderer-ndash-the-road-to-hellhellip/</a></li><li><a href="https://connect.microsoft.com/SQLServer/feedback/details/540183/supported-rdl-object-model-rdlom">https://connect.microsoft.com/SQLServer/feedback/details/540183/supported-rdl-object-model-rdlom</a></li><li>this is the kind of bullshit that counts for helpful content on the net <a href="https://social.msdn.microsoft.com/Forums/en-US/86205ca4-13d0-4ca6-84f1-79797616f0f4/exclude-null-values-from-sum-and-avg-calculation?forum=sqlreportingservices">https://social.msdn.microsoft.com/Forums/en-US/86205ca4-13d0-4ca6-84f1-79797616f0f4/exclude-null-values-from-sum-and-avg-calculation?forum=sqlreportingservices</a> - =sum(forum_format * quality_of_community) = errorrrrrrrrr</li><li>multiple rdl xml schema in the same fucking project, completely different xml structure</li><ol><li>2005 generated with "new report wizard" in VS 20-fucking-13: &lt;Report xmlns="http://schemas.microsoft.com/sqlserver/reporting/2005/01/reportdefinition" xmlns:rd="http://schemas.microsoft.com/SQLServer/reporting/reportdesigner"&gt;</li><li>2008 &lt;Report xmlns="http://schemas.microsoft.com/sqlserver/reporting/2008/01/reportdefinition" xmlns:rd="http://schemas.microsoft.com/SQLServer/reporting/reportdesigner"&gt;</li><li>2009 from https://technet.microsoft.com/en-us/library/cc627465%28v=sql.105%29.aspx - &lt;Report xmlns:rd=http://schemas.microsoft.com/SQLServer/reporting/reportdesigner xmlns="http://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"&gt;</li><li>2010 &lt;Report xmlns:rd="http://schemas.microsoft.com/SQLServer/reporting/reportdesigner" xmlns:cl="http://schemas.microsoft.com/sqlserver/reporting/2010/01/componentdefinition" xmlns="http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition"&gt;</li><li>how many fucking versions??!</li><li><a href="http://stackoverflow.com/questions/15539859/what-is-the-difference-between-rdl-2008-schema-and-rdl-2010-schema-feature-wise">http://stackoverflow.com/questions/15539859/what-is-the-difference-between-rdl-2008-schema-and-rdl-2010-schema-feature-wise</a></li><li><a href="http://stackoverflow.com/questions/9974179/is-there-a-new-version-of-rdl-schema-for-sql-server-2012-denali">http://stackoverflow.com/questions/9974179/is-there-a-new-version-of-rdl-schema-for-sql-server-2012-denali</a></li><li><a href="http://stackoverflow.com/questions/29951653/ssrs-2008r2-visual-studio-2008-and-2008-and-2010-schemas">http://stackoverflow.com/questions/29951653/ssrs-2008r2-visual-studio-2008-and-2008-and-2010-schemas</a> - how to not end up with old schema?!</li><li><a href="https://social.msdn.microsoft.com/Forums/sqlserver/en-US/f4d14548-c592-4d8d-8185-ca683c421649/2010-schema-with-visual-studio-2010?forum=sqlreportingservices">https://social.msdn.microsoft.com/Forums/sqlserver/en-US/f4d14548-c592-4d8d-8185-ca683c421649/2010-schema-with-visual-studio-2010?forum=sqlreportingservices</a></li></ol><li>how do you upgrade a report schema? install a massive chunk of fucking sql server <a href="http://stackoverflow.com/questions/13170608/upgrade-my-rdlc-schema-from-2008-01-to-2010-01">http://stackoverflow.com/questions/13170608/upgrade-my-rdlc-schema-from-2008-01-to-2010-01</a></li><li>[17:54:48] john doe: Btw have you noticed that in Print Layout view the header doesn't expand if any of the textboxes have auto-grown? [17:55:14] Tim Abell: that's because ssrs is a piece of shit from 1990 [17:55:28] Tim Abell: and it thinks A4 is the ultimate display format [17:55:47] Tim Abell: you just have to guess how much space you'll need</li><li>the ordering of the xml in the proj file is unstable causing diff noise</li><li>subreports, icky <a href="http://bhushan.extreme-advice.com/subreport-in-ssrs/">http://bhushan.extreme-advice.com/subreport-in-ssrs/</a></li><ol><li>or nested tables <a href="http://stackoverflow.com/questions/11335655/filtering-nested-data-regions-in-ssrs">http://stackoverflow.com/questions/11335655/filtering-nested-data-regions-in-ssrs</a></li></ol><li>some things can only be achieved with subreports, and they have to be deployed separately from the main report, meaning they can get out of sync. enjoy the fear of not knowing if you'll break something else when you upload your new version of the subreport you depend on</li><li>no support for "time" data type <a href="http://stackoverflow.com/questions/3846378/displaying-time-in-reporting-services-2008">http://stackoverflow.com/questions/3846378/displaying-time-in-reporting-services-2008</a></li><li>The "View Report" button next to the parameters when running a report in VS is *always* greyed-out, even though it actually works.</li><li>wow that's mental, hidden reports show in details view and not in tile view in the ssrs web ui</li><li>the report editor has a copy option for report items, but no paste, so you can't duplicate reports</li><ol><li>actually you can, but only if you know the keyboard shortcuts. 0_o - ctrl-c ctrl-v </li></ol><li>duplicating a report on the filesystem, and then using "add existing item" to include it puts it at the end of the list... until you rename it and then it's moved into alphabetical order causing a spurious diff. should have put in the right place in the first place. grr.</li><li>using the cursor keys to move textboxes around is so laggy that I overshoot every single time</li><li>the editor popups in visual studio are modal, so you can't refer to anything else</li><li>and there's no maximise button so you have to drag the fiddly border to make it bigger</li><li>the report editor hasn't heard of ctrl-c or ctrl-v, have to use ctrl-Ins / shift-Ins instead</li><li>border rendering / precedence is a fucking mess. set some borders, your report will look like a two-year-old coloured it in, and how it looks changes depending on the zoom level.</li><li>you have to use VB to do alternate row colours - <a href="http://stackoverflow.com/questions/44376/add-alternating-row-color-to-sql-server-reporting-services-report">http://stackoverflow.com/questions/44376/add-alternating-row-color-to-sql-server-reporting-services-report</a></li><li>if anything goes wrong with an expression all you get is "#Error". Helpful. E.g. <a href="http://stackoverflow.com/q/9144312/10245">http://stackoverflow.com/q/9144312/10245</a></li><li>this one time, at band camp, I edited a report definition in VS and it refused to save the new definition to disk (ctrl-shift-s, ctrl-shift-s!!). wtf. Restarted VS and all the changes were gone.</li><li>report editor silently adds new parameters to the report when you add new parameters to the sql. seriously. fuck off.</li><li>RSI-inducing UI for editing the reports. click click click clickity click</li><li>the sql editor has only a single undo. like ye olde notepad.</li><li>in the editor, you can right-click copy, you can't right-click paste. wtf. ctrl-v does paste though. wtf again. I know, I already said it, but it's reaaaaaly shit</li><li>the field list on a dataset is ordinal, allowing you to mismatch the select in the sql from the list of fields in the dataset and not notice</li><li>how do you align a textbox on the page?<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Top&gt;0.82546cm&lt;/Top&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Left&gt;0.07309cm&lt;/Left&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Height&gt;0.88964cm&lt;/Height&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Width&gt;2.3025cm&lt;/Width&gt;<br />fuck you!!!!</li><li>one goddam cell in the underlying format:</li></ol>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;TablixCell&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;CellContents&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Textbox Name="qty"&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;CanGrow&gt;true&lt;/CanGrow&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;KeepTogether&gt;true&lt;/KeepTogether&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Paragraphs&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Paragraph&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;TextRuns&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;TextRun&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Value&gt;=Sum(Fields!qty.Value)&lt;/Value&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Style /&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/TextRun&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/TextRuns&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Style /&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/Paragraph&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/Paragraphs&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;rd:DefaultName&gt;qty&lt;/rd:DefaultName&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Style&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Border&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Color&gt;LightGrey&lt;/Color&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;Style&gt;None&lt;/Style&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/Border&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;PaddingLeft&gt;2pt&lt;/PaddingLeft&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;PaddingRight&gt;2pt&lt;/PaddingRight&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;PaddingTop&gt;2pt&lt;/PaddingTop&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;PaddingBottom&gt;2pt&lt;/PaddingBottom&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/Style&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/Textbox&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/CellContents&gt;<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/TablixCell&gt;<br /><br />Contributed (thanks, a nice surprise!):<br /><br />71. Report width limited to 455in (even if I'm hiding columns using parameters against the Visibility column filter).<br />72. NO DYNAMIC COLUMN CREATION (ridiculous!)<br />73.  Selection of multiple columns and setting attributes is ridiculously  flaky. This is because I wanted to reduce the column width and font to  comply with Point 71 !!<br />74. We have to restart Reporting Server services frequently or our charts won't show up. Eh?<br />75. Cut and paste columns? Nope!<br /><br />More recent things:<br /><br />76. Disappearing "Report Data" menu: <a href="http://stackoverflow.com/a/28883272/10245">http://stackoverflow.com/a/28883272/1024</a><br />77. SSDT for VS2015 upgrades reports to 2016 schema as soon as they're opened (WAT?!)&nbsp; and ignores the TargetServerVersion being set to &lt;=2014 <a href="http://stackoverflow.com/questions/37816216/deploy-of-a-report-with-ssdt-2016-generates-error">http://stackoverflow.com/questions/37816216/deploy-of-a-report-with-ssdt-2016-generates-error</a> what if we haven't upgraded our production server, hmmm?<br />78. Okay so when you run a build, VS2015 then <b>downgrades</b> the rdl to the right schema to match the project's  target server version before putting it in the build folder. What could possssssibly go wrong. 0_o &nbsp; Complexity++ <br />79. Install SSRS in only 41 easy steps <a href="https://thecodeattic.wordpress.com/category/ssrs/">https://thecodeattic.wordpress.com/category/ssrs/</a><br />80. Build &gt; "Skipping 'SomeReport.rdl'. Item is up to date." - No it isn't, I've deleted it from the friggin bin folder. So clearly it has some stupid cache of what's it thinks is on disk rather than, oh I don't know fucking checking the disk. Sheesh. If it's that optimized why is everything still so damn slow?!<br />81. Building a project with lots of reports is slow. Even if nothing changed.<br />82. Intermittently get <i>"[rsInvalidReportDefinition] The definition of this report is not valid or supported by this version of Reporting Services. The report definition may have been created with a later version of Reporting Services, or contain content that is not well-formed or not valid based on Reporting Services schemas. Details: Data at the root level is invalid."</i> - I am not alone. <a href="https://connect.microsoft.com/SQLServer/feedback/details/2988044/randomly-get-rsinvalidreportdefinition-when-previewing-report">https://connect.microsoft.com/SQLServer/feedback/details/2988044/randomly-get-rsinvalidreportdefinition-when-previewing-report</a> - A rebuild fixes it for me, for a while at least.<br />83. Sometimes when you edit an embedded dataset it completely fails to persist any of your changes to disk. And when you close the report they are lost. Handy. Thanks fuck for git.<br />83. Assumes you've never heard of source control and creates numbered backups of report files (notably on auto-upgrade). Also has messages like "<i>delete will permanently delete this thing</i>" - no it won't I have source control; I wonder if the SSRS know what that is.<br />84. I've never managed to crash VS2015 so many times in one day. Omg you didn't click there did you? I wasn't ready! *crash* ... *again*<br />85. Change the files on disk and the preview window often doesn't notice<br />86. Preview window silently fires a 'build' of the reports. Sometimes.<br />87. Generates broken Shared-datasets <a href="http://stackoverflow.com/a/38753141/10245">http://stackoverflow.com/a/38753141/10245</a><br />88. If you break the xml of a shared-dataset the <i>entire project</i> will fail to load. w-t-f.<br />89. Renaming datasets etc just breaks everything rather than updating references.<br />90. The .rptproj file has a &lt;state&gt; tag at the top which is base64 encode xml (WAT?! xml in xml. eerrrrr), which is information about source control (<i>arse-about-face or what! source code that controls the *source-control* [that controls the source, that controls the source-control that controls the source...]; even the words are circular!!</i>). In the base64 you'll find a &lt;SourceControlInfo&gt; tag.<br /><br />&lt;Project xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" ToolsVersion="2.0"&gt; <br />&lt;State&gt;$base64$PFNvdXJjZUNvbnRyb2xJbmZvIHhtbG5zOnhzZD0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEiIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhtbG5zOmRkbDI9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDAzL2VuZ2luZS8yIiB4bWxuczpkZGwyXzI9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDAzL2VuZ2luZS8yLzIiIHhtbG5zOmRkbDEwMF8xMDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDA4L2VuZ2luZS8xMDAvMTAwIiB4bWxuczpkZGwyMDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDEwL2VuZ2luZS8yMDAiIHhtbG5zOmRkbDIwMF8yMDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDEwL2VuZ2luZS8yMDAvMjAwIiB4bWxuczpkZGwzMDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDExL2VuZ2luZS8zMDAiIHhtbG5zOmRkbDMwMF8zMDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDExL2VuZ2luZS8zMDAvMzAwIiB4bWxuczpkZGw0MDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDEyL2VuZ2luZS80MDAiIHhtbG5zOmRkbDQwMF80MDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDEyL2VuZ2luZS80MDAvNDAwIiB4bWxuczpkZGw1MDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDEzL2VuZ2luZS81MDAiIHhtbG5zOmRkbDUwMF81MDA9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vYW5hbHlzaXNzZXJ2aWNlcy8yMDEzL2VuZ2luZS81MDAvNTAwIiB4bWxuczpkd2Q9Imh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vRGF0YVdhcmVob3VzZS9EZXNpZ25lci8xLjAiPg0KICA8RW5hYmxlZD50cnVlPC9FbmFibGVkPg0KICA8UHJvamVjdE5hbWU+U0FLPC9Qcm9qZWN0TmFtZT4NCiAgPEF1eFBhdGg+U0FLPC9BdXhQYXRoPg0KICA8TG9jYWxQYXRoPlNBSzwvTG9jYWxQYXRoPg0KICA8UHJvdmlkZXI+U0FLPC9Qcm92aWRlcj4NCjwvU291cmNlQ29udHJvbEluZm8+&lt;/State&gt;<br />...<br /><br />decoded "state" contents:<br /><br />&nbsp; &lt;SourceControlInfo xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ddl2="http://schemas.microsoft.com/analysisservices/2003/engine/2" xmlns:ddl2_2="http://schemas.microsoft.com/analysisservices/2003/engine/2/2" xmlns:ddl100_100="http://schemas.microsoft.com/analysisservices/2008/engine/100/100" xmlns:ddl200="http://schemas.microsoft.com/analysisservices/2010/engine/200" xmlns:ddl200_200="http://schemas.microsoft.com/analysisservices/2010/engine/200/200" xmlns:ddl300="http://schemas.microsoft.com/analysisservices/2011/engine/300" xmlns:ddl300_300="http://schemas.microsoft.com/analysisservices/2011/engine/300/300" xmlns:ddl400="http://schemas.microsoft.com/analysisservices/2012/engine/400" xmlns:ddl400_400="http://schemas.microsoft.com/analysisservices/2012/engine/400/400" xmlns:ddl500="http://schemas.microsoft.com/analysisservices/2013/engine/500" xmlns:ddl500_500="http://schemas.microsoft.com/analysisservices/2013/engine/500/500" xmlns:dwd="http://schemas.microsoft.com/DataWarehouse/Designer/1.0"&gt;<br />&nbsp; &lt;Enabled&gt;true&lt;/Enabled&gt;<br />&nbsp; &lt;ProjectName&gt;SAK&lt;/ProjectName&gt;<br />&nbsp; &lt;AuxPath&gt;SAK&lt;/AuxPath&gt;<br />&nbsp; &lt;LocalPath&gt;SAK&lt;/LocalPath&gt;<br />&nbsp; &lt;Provider&gt;SAK&lt;/Provider&gt;<br />&lt;/SourceControlInfo&gt;<br /><br />Enough xml namespaces for you? <br /><br />91. The state base64 changes all the time causing diff noise.<br /><br /><br />I know I can't count, but if ssrs is going to make so little effort I don't see why I should. And to be honest "100" seemed a lot more like comic exaggeration when I titled my tomboy note which only had 5 or 6 grumblings in it, I wasn't actually expecting to get within spitting distance of the original number!<br /><br /><br />Doesn't mean I won't use it again mind, just don't promise to like it.<br /><br />If you liked this, you might also like the ssrs deployment tool I sometimes look after: <a href="https://github.com/timabell/ssrs-powershell-deploy">https://github.com/timabell/ssrs-powershell-deploy</a> (mostly not my work, just pulled together a bunch of contributions). <br /><br /><br />