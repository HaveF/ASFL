A Short Faq for Leo-editor
===========================

Leo-editor is a great tool. It was written by [Edward K. Ream], and contributed by many other warmhearted man.

You can find tutorial and user's guide at [Leo-editor home page](http://webpages.charter.net/edreamleo/front.html).

In fact, this short faq is my second iteration study notes of Leo-editor ;-)

I'll give thanks to [Edward K. Ream], [Terry Brown], [Ville M. Vainio] ... who help me to understand Leo-editor features.

[Edward K. Ream]: http://webpages.charter.net/edreamleo/ekr.html
[Terry Brown]: https://plus.google.com/116859937287332241707
[Ville M. Vainio]: https://plus.google.com/103097156557482112329/

***

* [Basic Concepts](#basic-concepts)
	* [UNL](#unl)
	* [Marked Node](#marked-node)
* [Combine with Other Editor](#combine-with-other-editor)
	* [Sync](#sync)
	* [Export to External Files](#export-to-external-files)

***

# Basic Concepts
## UNL
1. Q: the UNL (Uniform Node Location), the path from the top of the outline to the selected node, will be showed at the status area. 
but, how to use UNL? or, this message is not important, only prompt the user where he is?

> A1: They are useful as bookmarks.  You can right-click select all / copy
> them, then paste them into a node, as the first line.  Make the
> headline of the node something like "@url link to priority items", then
> when you double click that node, Leo will jump to the place where you
> copied the UNL, even opening another outline if needed (i.e. if the UNL
> you copied was in a different outline).

> A2: Although I double click the node will prompt I can change the content of headline, but when I press ctrl key, and click, it jumps!

## Marked Node
1. A red vertical bar denote the node is marked, but when the node need marked?
could you give me examples? thanks!

> A1: One use case (that I personally use) is the clone-marked command. There are many others

> A2: Thanks.
> I tried this command(clone-marked). This just like I choose multiple nodes and clone them at once.
> The marked function like ctrl+click to choose multiples nodes, and "unmark all" means release ctrl key.

> A3: Some more commands related to marks:
> 
> - unmark-all (c.unmarkAll)
> - move-marked
> - run-marked-unit-tests-externally
> - run-marked-unit-tests-locally
>
> The settings box for the find/change commands contains two check
> boxes: "mark changes" and "mark finds".  For example, if you enable
> "mark finds", all nodes found during a search.  Now use the
> move-marked or clone-marked commands to gather the found nodes.


# Combine with Other Editor
## Sync
1. Q: Sometimes, we use leo as project mangement tools, and edit the @file nodes or @shadow nodes outside. How to make sure these files are in sync state?

> A1: If we change one file outside, and then want to change it in leo, we can right click the node, choose "refresh from disk", then we can change it in leo, save...

> A2: If we change several files outside, and after that, it would be trouble to refresh them one by one, in this situation, close leo file, "reload it again" is the easiest.
> Please see the following FAQ entry for several tricks related ot
> [reloading Leo](http://webpages.charter.net/edreamleo/FAQ.html#how-can-i-use-leo-to-develop-leo-itself)

## Export to External Files
1. Q: The obvious way to write an external file would be to write the @file node itself followed by all the descendant nodes in outline order. Leo export all descendant(refer to @file node) nodes to external files?

> A1: No, if you reate an @file node, omit @others and @all and see what happens :-)  (You will get an error.) 
> like:
>>  errors writing: \<string-file\> 

>>  Orphan node

> ps-1: Leo handles scripts differently.  It is valid for a script not to
> include descendant nodes.  That is, you won't get an error if a script
> has descendants but does not include them with @others.  This is so
> descendant nodes can contain data.

> ps-2 A: Can contain data?  but why I contain data there? If the data is big, it should be at a separate file. Smaller data? Belonging to script?
> Could you give me a *real data example* which you are using?

> ps-2 B: There are many examples in unitTest.leo.  There are several advantages
> to using separate nodes for small (or not-so-small) data:

> 1.  The data is associated with the script (possibly in an @test node).
> 2.  There is no need for putting the data in a separate file.
> 3.  Putting the data in a node often simplifies the script.

> Take a look at unitTest.leo.  In general I do not like auxiliary
> files, especially those connected with unit tests.

