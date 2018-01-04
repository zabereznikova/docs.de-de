---
title: Entwurfszeitfehler im Windows Forms-Designer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62addf82929174d887160dadc4504cec19d9e3ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="39306-102">Entwurfszeitfehler im Windows Forms-Designer</span><span class="sxs-lookup"><span data-stu-id="39306-102">Design-Time Errors in the Windows Forms Designer</span></span>
<span data-ttu-id="39306-103">In diesem Thema wird die Bedeutung und der Verwendungszweck der Entwurfszeitfehlerliste erläutert, die in Microsoft Visual Studio angezeigt wird, wenn der Windows Forms-Designer nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="39306-103">This topic explains the meaning and use of the design-time error list that appears in Microsoft Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="39306-104">Wenn diese Fehlerliste angezeigt wird, sollten Sie sie nicht als Fehler im Designer, sondern als Hilfe beim Beheben von Fehlern in Ihrem Code interpretieren.</span><span class="sxs-lookup"><span data-stu-id="39306-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>  
  
 <span data-ttu-id="39306-105">Ein grundlegendes Verständnis dieser Fehlerliste hilft Ihnen beim Debuggen Ihrer Anwendungen, indem detaillierte Informationen zu den Fehlern und mögliche Lösungen vorgeschlagen werden.</span><span class="sxs-lookup"><span data-stu-id="39306-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>  
  
## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="39306-106">Die Schnittstelle für Entwurfszeitfehlerliste</span><span class="sxs-lookup"><span data-stu-id="39306-106">The Design-Time Error List Interface</span></span>  
 <span data-ttu-id="39306-107">Wenn der Windows Forms-Designer nicht geladen werden kann, wird im Designer eine Fehlerliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39306-107">If the Windows Forms Designer fails to load, an error list will appear in the designer.</span></span> <span data-ttu-id="39306-108">Die Fehler werden in Kategorien gruppiert.</span><span class="sxs-lookup"><span data-stu-id="39306-108">The errors are grouped into categories.</span></span> <span data-ttu-id="39306-109">Wenn Sie beispielsweise über vier Instanzen von nicht deklarierten Variablen verfügen, werden diese in der gleichen Fehlerkategorie gruppiert.</span><span class="sxs-lookup"><span data-stu-id="39306-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="39306-110">Jede Fehlerkategorie enthält eine kurze Beschreibung, die den Fehler zusammenfasst.</span><span class="sxs-lookup"><span data-stu-id="39306-110">Each error category includes a brief description that summarizes the error.</span></span>  
  
 <span data-ttu-id="39306-111">Sie können eine Fehlerkategorie erweitern oder reduzieren, indem Sie auf die Überschrift der Fehlerkategorie klicken oder indem Sie auf das Chevron zum Erweitern/Reduzieren klicken.</span><span class="sxs-lookup"><span data-stu-id="39306-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="39306-112">Wenn Sie eine Fehlerkategorie erweitern, wird folgende zusätzliche Hilfe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="39306-112">When you expand an error category, the following additional help is displayed:</span></span>  
  
-   <span data-ttu-id="39306-113">Instanzen dieses Fehlers.</span><span class="sxs-lookup"><span data-stu-id="39306-113">Instances of this error.</span></span>  
  
-   <span data-ttu-id="39306-114">Hilfe zu diesem Fehler.</span><span class="sxs-lookup"><span data-stu-id="39306-114">Help with this error.</span></span>  
  
-   <span data-ttu-id="39306-115">Forenbeiträge zu diesem Fehler.</span><span class="sxs-lookup"><span data-stu-id="39306-115">Forum posts about this error.</span></span>  
  
### <a name="instances-of-this-error"></a><span data-ttu-id="39306-116">Instanzen dieses Fehlers</span><span class="sxs-lookup"><span data-stu-id="39306-116">Instances of This Error</span></span>  
 <span data-ttu-id="39306-117">In der zusätzlichen Hilfe werden alle Instanzen des Fehlers im aktuellen Projekt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="39306-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="39306-118">Viele Fehler enthalten eine genaue Position im folgenden Format: *[Projektname]* *[Formularname]* Zeile:*[Zeilennummer]* Spalte:*[Spaltennummer]*.</span><span class="sxs-lookup"><span data-stu-id="39306-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="39306-119">Über den Link **Gehe zu Code** gelangen Sie zu der Position im Code, an der der Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="39306-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>  
  
 <span data-ttu-id="39306-120">Wenn dem Fehler eine Aufrufliste zugeordnet ist, können Sie zur näheren Erläuterung des Fehlers auf den Link **Aufrufliste anzeigen** klicken, um die Aufrufliste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="39306-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="39306-121">Durch Überprüfen des Stapels können Sie wertvolle Debuginformationen erhalten.</span><span class="sxs-lookup"><span data-stu-id="39306-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="39306-122">Sie können beispielsweise die Funktionen nachverfolgen, die vor Auftreten des Fehlers aufgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="39306-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="39306-123">Die Aufrufliste ist auswählbar, sodass sie kopiert und gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="39306-123">The call stack is selectable so that you can copy and save it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39306-124">In Visual Basic wird in der Entwurfszeit-Fehlerliste nicht mehr als ein Fehler angezeigt, es können jedoch mehrere Instanzen desselben Fehlers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="39306-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="39306-125">In Visual C++ weisen die Fehler keine Verknüpfungen mit GoTo-Codes/Zeilennummern auf.</span><span class="sxs-lookup"><span data-stu-id="39306-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>  
  
### <a name="help-with-this-error"></a><span data-ttu-id="39306-126">Hilfe zu diesem Fehler</span><span class="sxs-lookup"><span data-stu-id="39306-126">Help with This Error</span></span>  
 <span data-ttu-id="39306-127">Wenn der Fehler einen Link zu einem MSDN-Hilfethema enthält, umfasst die zusätzliche Hilfe einen Link zum Hilfethema.</span><span class="sxs-lookup"><span data-stu-id="39306-127">If the error contains a link to an associated MSDN help topic, the additional help will include a link to the help topic.</span></span> <span data-ttu-id="39306-128">Wenn Sie auf den Link klicken, wird das zugehörige Hilfethema in Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39306-128">When you click the link, the associated help topic appears in Visual Studio.</span></span>  
  
### <a name="forum-posts-about-this-error"></a><span data-ttu-id="39306-129">Forumbeiträge zu diesem Fehler</span><span class="sxs-lookup"><span data-stu-id="39306-129">Forum posts about this error</span></span>  
 <span data-ttu-id="39306-130">Die zusätzliche Hilfe umfasst einen Link zu MSDN-Forenbeiträgen zu dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="39306-130">The additional help will include a link to MSDN forum posts related to the error.</span></span> <span data-ttu-id="39306-131">Die Foren werden basierend auf der Zeichenfolge der Fehlermeldung durchsucht.</span><span class="sxs-lookup"><span data-stu-id="39306-131">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="39306-132">Sie können auch die folgenden Foren durchsuchen:</span><span class="sxs-lookup"><span data-stu-id="39306-132">You can also try searching the following forums:</span></span>  
  
-   [<span data-ttu-id="39306-133">Forum von Windows Forms-Designer</span><span class="sxs-lookup"><span data-stu-id="39306-133">Windows Forms Designer Forum</span></span>](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [<span data-ttu-id="39306-134">Windows Forms-Foren</span><span class="sxs-lookup"><span data-stu-id="39306-134">Windows Forms Forums</span></span>](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a><span data-ttu-id="39306-135">Ignorieren und fortfahren</span><span class="sxs-lookup"><span data-stu-id="39306-135">Ignore and Continue</span></span>  
 <span data-ttu-id="39306-136">Sie können die Fehlerbedingung ignorieren und mit dem Laden des Designers fortfahren.</span><span class="sxs-lookup"><span data-stu-id="39306-136">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="39306-137">Die Auswahl dieser Aktion kann zu unerwartetem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="39306-137">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="39306-138">Beispielsweise werden Steuerelemente möglicherweise nicht auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39306-138">For example, controls may not appear on the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39306-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39306-139">See Also</span></span>  
 [<span data-ttu-id="39306-140">Problembehandlung bei der Entwicklung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="39306-140">Troubleshooting Design-Time Development</span></span>](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [<span data-ttu-id="39306-141">Problembehandlung beim Erstellen von Komponenten und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="39306-141">Troubleshooting Control and Component Authoring</span></span>](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 [<span data-ttu-id="39306-142">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="39306-142">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="39306-143">Fehlermeldungen im Windows Forms-Designer</span><span class="sxs-lookup"><span data-stu-id="39306-143">Windows Forms Designer Error Messages</span></span>](http://msdn.microsoft.com/en-us/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)
