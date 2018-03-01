---
title: "Übersicht über das BindingNavigator-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 921f8c7791620d51107fa2ff31a637094fc0c633
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="bindingnavigator-control-overview-windows-forms"></a><span data-ttu-id="b0b83-102">Übersicht über das BindingNavigator-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b0b83-102">BindingNavigator Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b0b83-103">Mit dem <xref:System.Windows.Forms.BindingNavigator>-Steuerelement können Sie ein standardisiertes Instrument erstellen, mit dem Benutzer Daten in einem Windows Form suchen und ändern können.</span><span class="sxs-lookup"><span data-stu-id="b0b83-103">You can use the <xref:System.Windows.Forms.BindingNavigator> control to create a standardized means for users to search and change data on a Windows Form.</span></span> <span data-ttu-id="b0b83-104"><xref:System.Windows.Forms.BindingNavigator> wird häufig zusammen mit der <xref:System.Windows.Forms.BindingSource>-Komponente verwendet, damit Benutzer Datensätze in einem Formular durchlaufen und bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="b0b83-104">You frequently use <xref:System.Windows.Forms.BindingNavigator> with the <xref:System.Windows.Forms.BindingSource> component to enable users to move through data records on a form and interact with the records.</span></span>  
  
## <a name="how-the-bindingnavigator-works"></a><span data-ttu-id="b0b83-105">So funktioniert der BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="b0b83-105">How the BindingNavigator Works</span></span>  
 <span data-ttu-id="b0b83-106">Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement besteht aus einem <xref:System.Windows.Forms.ToolStrip>-Objekt mit einer Reihe von <xref:System.Windows.Forms.ToolStripItem>-Objekten für die meisten gängigen datenbezogenen Aktionen: Hinzufügen von Daten, Löschen von Daten und Navigieren durch Daten.</span><span class="sxs-lookup"><span data-stu-id="b0b83-106">The <xref:System.Windows.Forms.BindingNavigator> control is composed of a <xref:System.Windows.Forms.ToolStrip> with a series of <xref:System.Windows.Forms.ToolStripItem> objects for most of the common data-related actions: adding data, deleting data, and navigating through data.</span></span> <span data-ttu-id="b0b83-107">Standardmäßig enthält das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement enthält diese Standardschaltflächen.</span><span class="sxs-lookup"><span data-stu-id="b0b83-107">By default, the <xref:System.Windows.Forms.BindingNavigator> control contains these standard buttons.</span></span> <span data-ttu-id="b0b83-108">Die folgende Abbildung zeigt das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="b0b83-108">The following screen shot shows the <xref:System.Windows.Forms.BindingNavigator> control on a form.</span></span>  
  
 <span data-ttu-id="b0b83-109">![BindingNavigator-Steuerelement](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "CpDataContainerCtrl")</span><span class="sxs-lookup"><span data-stu-id="b0b83-109">![BindingNavigator Control](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "cpDataContainerCtrl")</span></span>  
  
 <span data-ttu-id="b0b83-110">In der folgende Tabelle sind die Steuerelemente aufgelistet und deren Funktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0b83-110">The following table lists the controls and describes their functions.</span></span>  
  
|<span data-ttu-id="b0b83-111">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b0b83-111">Control</span></span>|<span data-ttu-id="b0b83-112">Funktion</span><span class="sxs-lookup"><span data-stu-id="b0b83-112">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="b0b83-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A>-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b0b83-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> button</span></span>|<span data-ttu-id="b0b83-114">Fügt eine neue Zeile in der zugrunde liegenden Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="b0b83-114">Inserts a new row into the underlying data source.</span></span>|  
|<span data-ttu-id="b0b83-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A>-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b0b83-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button</span></span>|<span data-ttu-id="b0b83-116">Löscht die aktuelle Zeile aus der zugrunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="b0b83-116">Deletes the current row from the underlying data source.</span></span>|  
|<span data-ttu-id="b0b83-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b0b83-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button</span></span>|<span data-ttu-id="b0b83-118">Wechselt zum ersten Element in der zugrunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="b0b83-118">Moves to the first item in the underlying data source.</span></span>|  
|<span data-ttu-id="b0b83-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A>-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b0b83-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> button</span></span>|<span data-ttu-id="b0b83-120">Wechselt zum letzten Element in der zugrunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="b0b83-120">Moves to the last item in the underlying data source.</span></span>|  
|<span data-ttu-id="b0b83-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A>-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b0b83-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> button</span></span>|<span data-ttu-id="b0b83-122">Wechselt zum nächsten Element in der zugrunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="b0b83-122">Moves to the next item in the underlying data source.</span></span>|  
|<span data-ttu-id="b0b83-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A>-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b0b83-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> button</span></span>|<span data-ttu-id="b0b83-124">Wechselt zum vorherigen Element in der zugrunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="b0b83-124">Moves to the previous item in the underlying data source.</span></span>|  
|<span data-ttu-id="b0b83-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A>-Textfeld</span><span class="sxs-lookup"><span data-stu-id="b0b83-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> text box</span></span>|<span data-ttu-id="b0b83-126">Gibt die aktuelle Position in der zugrunde liegenden Datenquelle zurück.</span><span class="sxs-lookup"><span data-stu-id="b0b83-126">Returns the current position within the underlying data source.</span></span>|  
|<span data-ttu-id="b0b83-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A>-Textfeld</span><span class="sxs-lookup"><span data-stu-id="b0b83-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> text box</span></span>|<span data-ttu-id="b0b83-128">Gibt die Gesamtzahl von Elementen in der zugrunde liegenden Datenquelle zurück.</span><span class="sxs-lookup"><span data-stu-id="b0b83-128">Returns the total number of items in the underlying data source.</span></span>|  
  
 <span data-ttu-id="b0b83-129">Für jedes Steuerelement in dieser Auflistung gibt es einen entsprechenden Member der <xref:System.Windows.Forms.BindingSource>-Komponente, die dieselbe Funktionalität programmgesteuert bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b0b83-129">For each control in this collection, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically provides the same functionality.</span></span> <span data-ttu-id="b0b83-130">Beispielsweise entspricht die <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>-Schaltfläche der <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>-Methode der <xref:System.Windows.Forms.BindingSource>-Komponente, die <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A>-Schaltfläche der <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A>-Methode usw.</span><span class="sxs-lookup"><span data-stu-id="b0b83-130">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span>  
  
 <span data-ttu-id="b0b83-131">Wenn die Standardschaltflächen für Ihre Anwendung nicht geeignet sind, oder wenn Sie weitere Schaltflächen benötigen, um andere Funktionalitäten zu unterstützen, können Sie Ihre eigenen <xref:System.Windows.Forms.ToolStrip>-Schaltflächen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b0b83-131">If the default buttons are not suited to your application, or if you require additional buttons to support other types of functionality, you can supply your own <xref:System.Windows.Forms.ToolStrip> buttons.</span></span> <span data-ttu-id="b0b83-132">Siehe auch [Vorgehensweise: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="b0b83-132">Also see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b83-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0b83-133">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="b0b83-134">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b0b83-134">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
