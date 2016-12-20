---
title: "Creating Mutually Exclusive Checkboxes (C#) | Microsoft Docs"
author: wenz
description: "When only one of a set of options may be selected, radio buttons are usually used. There is a drawback, though: Once one radio button in a group is selected,..."
ms.author: riande
manager: wpickett
ms.date: 06/02/2008
ms.topic: article
ms.assetid: 
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/mutuallyexclusivecheckbox/creating-mutually-exclusive-checkboxes-cs
---
[Edit .md file](C:\Projects\msc\dev\Msc.Www\Web.ASP\App_Data\github\web-forms\overview\ajax-control-toolkit\mutuallyexclusivecheckbox\creating-mutually-exclusive-checkboxes-cs.md) | [Edit dev content](http://www.aspdev.net/umbraco#/content/content/edit/24832) | [View dev content](http://docs.aspdev.net/tutorials/web-forms/overview/ajax-control-toolkit/mutuallyexclusivecheckbox/creating-mutually-exclusive-checkboxes-cs.html) | [View prod content](http://www.asp.net/web-forms/overview/ajax-control-toolkit/mutuallyexclusivecheckbox/creating-mutually-exclusive-checkboxes-cs) | Picker: 33132

Creating Mutually Exclusive Checkboxes (C#)
====================
by [Christian Wenz](https://github.com/wenz)

[Download Code](http://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/MutuallyExclusiveCheckBox0.cs.zip) or [Download PDF](http://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/mutuallyexclusivecheckbox0CS.pdf)

> When only one of a set of options may be selected, radio buttons are usually used. There is a drawback, though: Once one radio button in a group is selected, it is not possible to uncheck all radio buttons. Check boxes can be unchecked at any time, however are not mutually exclusive. This tutorial provides the best of both approaches: check boxes that are mutually exclusive.


## Overview

When only one of a set of options may be selected, radio buttons are usually used. There is a drawback, though: Once one radio button in a group is selected, it is not possible to uncheck all radio buttons. Check boxes can be unchecked at any time, however are not mutually exclusive. This tutorial provides the best of both approaches: check boxes that are mutually exclusive.

## Steps

The ASP.NET AJAX Control Toolkit contains the MutuallyExclusiveCheckBox extender. This enables programmers to assign any checkbox to a group name (`Key` attribute). From all check boxes within the same group, only one may be selected at one time.

Let's start with putting two check boxes on a new ASP.NET page. There can be more, but two of them suffice to demonstrate the principle:

    <asp:CheckBox ID="cbYes" runat="server" />Yes
    <asp:CheckBox ID="cbNo" runat="server" />No

For both checkboxes, a MutuallyExclusiveCheckBoxExtender control must be put on the page. Both Key attributes need to have the same value, just as the value attributes of HTML radio button elements must be identical to denote the group they belong to. The TargetControlID property of the extender points to the ID of the check box.

    <ajaxToolkit:MutuallyExclusiveCheckBoxExtender ID="mecbe1" runat="server"
     TargetControlID="cbYes" Key="YesNo" />
    <ajaxToolkit:MutuallyExclusiveCheckBoxExtender ID="mecbe2" runat="server"
     TargetControlID="cbNo" Key="YesNo" />

Finally, include the ASP.NET AJAX `ScriptManager` which is required by all elements of the ASP.NET AJAX Control Toolkit:

    <asp:ScriptManager ID="asm" runat="server" />

Save and run the page: You can check and uncheck both check boxes, however at no time can both check boxes be checked.


[![Only one checkbox can be checked at a time](creating-mutually-exclusive-checkboxes-cs/_static/image2.png)](creating-mutually-exclusive-checkboxes-cs/_static/image1.png)

Only one checkbox can be checked at a time ([Click to view full-size image](creating-mutually-exclusive-checkboxes-cs/_static/image3.png))

>[!div class="step-by-step"] [Next](creating-mutually-exclusive-checkboxes-vb.md)