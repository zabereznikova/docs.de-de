---
title: Entwickeln benutzerdefinierter Steuerelemente
description: Erfahren Sie mehr über Windows Forms-Steuerelemente. Insbesondere erfahren Sie, wie Sie vorhandene Steuerelemente kombinieren, vorhandene Steuerelemente erweitern und eigene benutzerdefinierte Steuerelemente erstellen.
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
ms.openlocfilehash: 12013496c9650489fdd7512206317000fc0ec78c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618375"
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="ddbd2-104">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ddbd2-104">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="ddbd2-105">Windows Forms-Steuerelemente sind wiederverwendbare Komponenten, die Funktionen der Benutzeroberfläche einschließen und in clientseitigen Windows-basierten Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-105">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="ddbd2-106">Windows Forms stellt nicht nur viele einsatzbereite Steuerelemente bereit, sondern auch die Infrastruktur für die Entwicklung eigener Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-106">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="ddbd2-107">Sie können vorhandene Steuerelemente kombinieren und erweitern oder eigene benutzerdefinierte Steuerelemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-107">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="ddbd2-108">Dieser Abschnitt enthält Hintergrundinformationen und Beispiele, die Sie beim Entwickeln von Windows Forms-Steuerelementen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-108">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddbd2-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ddbd2-109">In This Section</span></span>  
 [<span data-ttu-id="ddbd2-110">Übersicht über die Verwendung von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddbd2-110">Overview of Using Controls in Windows Forms</span></span>](overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="ddbd2-111">Hebt die wichtigsten Elemente der Verwendung von Steuerelementen in Windows Forms-Anwendungen hervor.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-111">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="ddbd2-112">Arten von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-112">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="ddbd2-113">Beschreibt die verschiedenen Arten benutzerdefinierter Steuerelemente, die Sie mit dem <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace erstellen können.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-113">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="ddbd2-114">Grundlagen für das Entwickeln von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-114">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)  
 <span data-ttu-id="ddbd2-115">Erläutert die ersten Schritte bei der Entwicklung von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-115">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="ddbd2-116">Eigenschaften von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)  
 <span data-ttu-id="ddbd2-117">Veranschaulicht, wie Eigenschaften zu Windows Forms-Steuerelementen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-117">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="ddbd2-118">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-118">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)  
 <span data-ttu-id="ddbd2-119">Zeigt, wie Ereignisse in Windows Forms-Steuerelementen behandelt und definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-119">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="ddbd2-120">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-120">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="ddbd2-121">Beschreibt die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-121">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="ddbd2-122">Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-122">Custom Control Painting and Rendering</span></span>](custom-control-painting-and-rendering.md)  
 <span data-ttu-id="ddbd2-123">Erläutert, wie die Darstellung von Steuerelementen angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-123">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="ddbd2-124">Layout in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-124">Layout in Windows Forms Controls</span></span>](layout-in-windows-forms-controls.md)  
 <span data-ttu-id="ddbd2-125">Veranschaulicht, wie Sie komplexe Layouts für Steuerelemente und Formulare erstellen können.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-125">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="ddbd2-126">Multithreading in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ddbd2-126">Multithreading in Windows Forms Controls</span></span>](multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="ddbd2-127">Veranschaulicht das Implementieren von Multithread-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-127">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ddbd2-128">Referenz</span><span class="sxs-lookup"><span data-stu-id="ddbd2-128">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="ddbd2-129">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-129">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="ddbd2-130">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-130">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ddbd2-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ddbd2-131">Related Sections</span></span>  
 <span data-ttu-id="ddbd2-132">[Entwurfszeitattribute für Komponenten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ddbd2-132">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="ddbd2-133">Listet die Metadatenattribute für Komponenten und Steuerelemente auf, damit sie in visuellen Designern zur Entwurfszeit korrekt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-133">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="ddbd2-134">[Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ddbd2-134">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="ddbd2-135">Beschreibt die Implementierung von Klassen wie Editoren und Designern, die Entwurfszeitunterstützung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-135">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 <span data-ttu-id="ddbd2-136">[Vorgehensweise: Lizenzieren von Komponenten und Steuerelementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ddbd2-136">[How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span></span>  
 <span data-ttu-id="ddbd2-137">Beschreibt das Implementieren einer Lizenzierung in ein Steuerelement oder eine Komponente.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-137">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="ddbd2-138">Siehe auch [Entwickeln von Windows Forms-Steuerelemente zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ddbd2-138">Also see [Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md).</span></span>
