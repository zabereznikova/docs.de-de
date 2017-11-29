---
title: Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89be7e347556c8ec34296044f17fbfd4450bc127
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="489df-102">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="489df-102">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="489df-103">Windows Forms-Steuerelemente sind wiederverwendbare Komponenten, die Funktionen der Benutzeroberfläche einschließen und in clientseitigen Windows-basierten Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="489df-103">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="489df-104">Windows Forms stellt nicht nur viele einsatzbereite Steuerelemente bereit, sondern auch die Infrastruktur für die Entwicklung eigener Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="489df-104">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="489df-105">Sie können vorhandene Steuerelemente kombinieren und erweitern oder eigene benutzerdefinierte Steuerelemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="489df-105">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="489df-106">Dieser Abschnitt enthält Hintergrundinformationen und Beispiele, die Sie beim Entwickeln von Windows Forms-Steuerelementen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="489df-106">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="489df-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="489df-107">In This Section</span></span>  
 [<span data-ttu-id="489df-108">Übersicht über die Verwendung von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="489df-108">Overview of Using Controls in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="489df-109">Hebt die wichtigsten Elemente der Verwendung von Steuerelementen in Windows Forms-Anwendungen hervor.</span><span class="sxs-lookup"><span data-stu-id="489df-109">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="489df-110">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="489df-110">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="489df-111">Beschreibt die verschiedenen Arten benutzerdefinierter Steuerelemente, die Sie mit dem <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace erstellen können.</span><span class="sxs-lookup"><span data-stu-id="489df-111">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="489df-112">Grundlagen für das Entwickeln von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-112">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)  
 <span data-ttu-id="489df-113">Erläutert die ersten Schritte bei der Entwicklung von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="489df-113">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="489df-114">Eigenschaften von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-114">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 <span data-ttu-id="489df-115">Veranschaulicht, wie Eigenschaften zu Windows Forms-Steuerelementen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="489df-115">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="489df-116">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-116">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 <span data-ttu-id="489df-117">Zeigt, wie Ereignisse in Windows Forms-Steuerelementen behandelt und definiert werden.</span><span class="sxs-lookup"><span data-stu-id="489df-117">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="489df-118">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-118">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="489df-119">Beschreibt die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können.</span><span class="sxs-lookup"><span data-stu-id="489df-119">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="489df-120">Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-120">Custom Control Painting and Rendering</span></span>](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="489df-121">Erläutert, wie die Darstellung von Steuerelementen angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="489df-121">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="489df-122">Layout in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-122">Layout in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/layout-in-windows-forms-controls.md)  
 <span data-ttu-id="489df-123">Veranschaulicht, wie Sie komplexe Layouts für Steuerelemente und Formulare erstellen können.</span><span class="sxs-lookup"><span data-stu-id="489df-123">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="489df-124">Multithreading in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-124">Multithreading in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="489df-125">Veranschaulicht das Implementieren von Multithread-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="489df-125">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="489df-126">Verweis</span><span class="sxs-lookup"><span data-stu-id="489df-126">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="489df-127">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="489df-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="489df-128">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="489df-128">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="489df-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="489df-129">Related Sections</span></span>  
 [<span data-ttu-id="489df-130">Entwurfszeitattribute für Komponenten</span><span class="sxs-lookup"><span data-stu-id="489df-130">Design-Time Attributes for Components</span></span>](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="489df-131">Listet die Metadatenattribute für Komponenten und Steuerelemente auf, damit sie in visuellen Designern zur Entwurfszeit korrekt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="489df-131">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="489df-132">Erweitern der Entwurfszeitunterstützung</span><span class="sxs-lookup"><span data-stu-id="489df-132">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="489df-133">Beschreibt die Implementierung von Klassen wie Editoren und Designern, die Entwurfszeitunterstützung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="489df-133">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 [<span data-ttu-id="489df-134">Vorgehensweise: Lizenzieren von Komponenten und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="489df-134">How to: License Components and Controls</span></span>](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)  
 <span data-ttu-id="489df-135">Beschreibt das Implementieren einer Lizenzierung in ein Steuerelement oder eine Komponente.</span><span class="sxs-lookup"><span data-stu-id="489df-135">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="489df-136">Siehe auch [Entwickeln von Windows Forms-Steuerelemente zur Entwurfszeit](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="489df-136">Also see [Developing Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span></span>
