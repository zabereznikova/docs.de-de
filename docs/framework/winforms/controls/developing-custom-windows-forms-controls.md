---
title: Entwickeln benutzerdefinierter Steuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
ms.openlocfilehash: 9dbc1c4530b3a0f4e579ca67c7ae88c1685222ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745999"
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="c0df4-102">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0df4-102">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="c0df4-103">Windows Forms-Steuerelemente sind wiederverwendbare Komponenten, die Funktionen der Benutzeroberfläche einschließen und in clientseitigen Windows-basierten Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0df4-103">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="c0df4-104">Windows Forms stellt nicht nur viele einsatzbereite Steuerelemente bereit, sondern auch die Infrastruktur für die Entwicklung eigener Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="c0df4-104">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="c0df4-105">Sie können vorhandene Steuerelemente kombinieren und erweitern oder eigene benutzerdefinierte Steuerelemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0df4-105">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="c0df4-106">Dieser Abschnitt enthält Hintergrundinformationen und Beispiele, die Sie beim Entwickeln von Windows Forms-Steuerelementen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c0df4-106">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0df4-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c0df4-107">In This Section</span></span>  
 [<span data-ttu-id="c0df4-108">Übersicht über die Verwendung von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0df4-108">Overview of Using Controls in Windows Forms</span></span>](overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="c0df4-109">Hebt die wichtigsten Elemente der Verwendung von Steuerelementen in Windows Forms-Anwendungen hervor.</span><span class="sxs-lookup"><span data-stu-id="c0df4-109">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="c0df4-110">Vielfalt benutzerdefinierter Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="c0df4-110">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="c0df4-111">Beschreibt die verschiedenen Arten benutzerdefinierter Steuerelemente, die Sie mit dem <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace erstellen können.</span><span class="sxs-lookup"><span data-stu-id="c0df4-111">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="c0df4-112">Grundlagen für das Entwickeln von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c0df4-112">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)  
 <span data-ttu-id="c0df4-113">Erläutert die ersten Schritte bei der Entwicklung von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="c0df4-113">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="c0df4-114">Eigenschaften von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c0df4-114">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)  
 <span data-ttu-id="c0df4-115">Veranschaulicht, wie Eigenschaften zu Windows Forms-Steuerelementen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c0df4-115">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c0df4-116">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c0df4-116">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)  
 <span data-ttu-id="c0df4-117">Zeigt, wie Ereignisse in Windows Forms-Steuerelementen behandelt und definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c0df4-117">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c0df4-118">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c0df4-118">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="c0df4-119">Beschreibt die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können.</span><span class="sxs-lookup"><span data-stu-id="c0df4-119">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="c0df4-120">Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c0df4-120">Custom Control Painting and Rendering</span></span>](custom-control-painting-and-rendering.md)  
 <span data-ttu-id="c0df4-121">Erläutert, wie die Darstellung von Steuerelementen angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0df4-121">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="c0df4-122">Layout in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c0df4-122">Layout in Windows Forms Controls</span></span>](layout-in-windows-forms-controls.md)  
 <span data-ttu-id="c0df4-123">Veranschaulicht, wie Sie komplexe Layouts für Steuerelemente und Formulare erstellen können.</span><span class="sxs-lookup"><span data-stu-id="c0df4-123">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="c0df4-124">Multithreading in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c0df4-124">Multithreading in Windows Forms Controls</span></span>](multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="c0df4-125">Veranschaulicht das Implementieren von Multithread-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="c0df4-125">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c0df4-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="c0df4-126">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="c0df4-127">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="c0df4-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="c0df4-128">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="c0df4-128">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c0df4-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c0df4-129">Related Sections</span></span>  
 <span data-ttu-id="c0df4-130">[Entwurfszeitattribute für Komponenten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c0df4-130">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="c0df4-131">Listet die Metadatenattribute für Komponenten und Steuerelemente auf, damit sie in visuellen Designern zur Entwurfszeit korrekt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0df4-131">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="c0df4-132">[Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c0df4-132">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="c0df4-133">Beschreibt die Implementierung von Klassen wie Editoren und Designern, die Entwurfszeitunterstützung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0df4-133">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 <span data-ttu-id="c0df4-134">[Vorgehensweise: Lizenzieren von Komponenten und Steuerelementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c0df4-134">[How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span></span>  
 <span data-ttu-id="c0df4-135">Beschreibt das Implementieren einer Lizenzierung in ein Steuerelement oder eine Komponente.</span><span class="sxs-lookup"><span data-stu-id="c0df4-135">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="c0df4-136">Siehe auch [Entwickeln von Windows Forms-Steuerelemente zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="c0df4-136">Also see [Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md).</span></span>
