---
title: Entwickeln von Steuerelementen zur Entwurfszeit
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7626e1efbb30ef3bfe9b5b1278c0adb18dd5944b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628708"
---
# <a name="develop-windows-forms-controls-at-design-time"></a><span data-ttu-id="d0da9-102">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="d0da9-102">Develop Windows Forms controls at design time</span></span>

<span data-ttu-id="d0da9-103">NET Framework bietet Autoren von Steuerelementen eine Fülle von Technologien zum Erstellen von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="d0da9-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="d0da9-104">Autoren sind nicht mehr darauf beschränkt, zusammengesetzte Steuerelemente zu entwerfen, die als Auflistung bereits vorhandener Steuerelemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0da9-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="d0da9-105">Durch Vererbung können Sie eigene Steuerelemente aus bereits vorhandenen zusammengesetzten Steuerelementen bzw. bereits vorhandenen Windows Forms-Steuerelementen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d0da9-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="d0da9-106">Sie können auch eigene Steuerelemente entwerfen, durch die das benutzerdefinierte Zeichnen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="d0da9-107">Dank dieser Möglichkeiten zeichnen sich sowohl die Entwurfsfeatures als auch die Funktionalität der grafischen Oberfläche durch eine hohe Flexibilität aus.</span><span class="sxs-lookup"><span data-stu-id="d0da9-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="d0da9-108">Um die Vorteile dieser Features nutzen zu können, sollten Sie mit den Konzepten der objektbasierten Programmierung vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="d0da9-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="d0da9-109">Es ist nicht erforderlich, ein umfassendes Verständnis der Vererbung zu haben, aber Sie finden es möglicherweise hilfreich, wenn Sie auf [Grundlagen der Vererbung (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)verweisen.</span><span class="sxs-lookup"><span data-stu-id="d0da9-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>

<span data-ttu-id="d0da9-110">Informationen zum Erstellen benutzerdefinierter Steuerelemente zur Verwendung in Web Forms finden Sie unter [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d0da9-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d0da9-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d0da9-111">In this section</span></span>

<span data-ttu-id="d0da9-112">Exemplarische Vorgehensweise [: Erstellen eines zusammengesetzten Steuer](walkthrough-authoring-a-composite-control-with-visual-csharp.md) Elements</span><span class="sxs-lookup"><span data-stu-id="d0da9-112">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="d0da9-113">Veranschaulicht das Erstellen eines einfachen zusammengesetzten Steuerelements in Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d0da9-113">Shows how to create a simple composite control in C#.</span></span>

<span data-ttu-id="d0da9-114">Exemplarische Vorgehensweise [: Vererben von einem Windows Forms-Steuer](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md) Element</span><span class="sxs-lookup"><span data-stu-id="d0da9-114">[Walkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="d0da9-115">Veranschaulicht, wie ein einfaches Windows Forms-Steuerelement unter Verwendung der Vererbung in Visual C# erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-115">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>

<span data-ttu-id="d0da9-116">Exemplarische [Vorgehensweise: Ausführen allgemeiner Aufgaben mithilfe von Designer Aktionen](perform-common-tasks-design-actions.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-116">[Walkthrough: Perform common tasks using designer actions](perform-common-tasks-design-actions.md)</span></span>\
<span data-ttu-id="d0da9-117">Veranschaulicht, wie das Smarttagfeature auf Windows Forms-Steuerelemente angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-117">Shows how to use the smart tag feature on Windows Forms controls.</span></span>

<span data-ttu-id="d0da9-118">Exemplarische Vorgehensweise [: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md) -</span><span class="sxs-lookup"><span data-stu-id="d0da9-118">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)</span></span>\
<span data-ttu-id="d0da9-119">Zeigt, wie das <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType>-Attribut verwendet wird, um eine Auflistung zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="d0da9-119">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>

<span data-ttu-id="d0da9-120">[Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-120">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="d0da9-121">Veranschaulicht das Debuggen des Verhaltens eines Windows Forms-Steuerelements zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="d0da9-121">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>

<span data-ttu-id="d0da9-122">Exemplarische Vorgehensweise [: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen](creating-a-wf-control-design-time-features.md) nutzt</span><span class="sxs-lookup"><span data-stu-id="d0da9-122">[Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md)</span></span>\
<span data-ttu-id="d0da9-123">Zeigt, wie ein zusammengesetztes Steuerelement nahtlos in die Entwurfsumgebung integriert wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-123">Shows how to tightly integrate a composite control into the design environment.</span></span>

<span data-ttu-id="d0da9-124">[Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](how-to-author-controls-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-124">[How to: Author Controls for Windows Forms](how-to-author-controls-for-windows-forms.md)</span></span>\
<span data-ttu-id="d0da9-125">Bietet einen Überblick über die Aspekte der Implementierung eines Windows Forms-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="d0da9-125">Provides an overview of considerations for implementing a Windows Forms control.</span></span>

<span data-ttu-id="d0da9-126">[Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](how-to-author-composite-controls.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-126">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>\
<span data-ttu-id="d0da9-127">Veranschaulicht, wie ein Steuerelement durch Vererbung von einem zusammengesetzten Steuerelement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-127">Shows how to create a control by inheriting from a composite control.</span></span>

<span data-ttu-id="d0da9-128">[Vorgehensweise: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-128">[How to: Inherit from the UserControl Class](how-to-inherit-from-the-usercontrol-class.md)</span></span>\
<span data-ttu-id="d0da9-129">Bietet eine Übersicht über das Verfahren zum Erstellen eines zusammengesetzten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="d0da9-129">Provides an overview of the procedure for creating a composite control.</span></span>

<span data-ttu-id="d0da9-130">[Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](how-to-inherit-from-existing-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-130">[How to: Inherit from Existing Windows Forms Controls](how-to-inherit-from-existing-windows-forms-controls.md)</span></span>\
<span data-ttu-id="d0da9-131">Zeigt, wie ein erweitertes Steuerelement erstellt wird, indem von der <xref:System.Windows.Forms.Button> Steuerelement Klasse geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-131">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>

<span data-ttu-id="d0da9-132">[Vorgehensweise: Erben von der Control-Klasse](how-to-inherit-from-the-control-class.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-132">[How to: Inherit from the Control Class](how-to-inherit-from-the-control-class.md)</span></span>\
<span data-ttu-id="d0da9-133">Bietet eine Übersicht über das Erstellen eines erweiterten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="d0da9-133">Provides an overview of creating an extended control.</span></span>

<span data-ttu-id="d0da9-134">Gewusst [wie: Ausrichten eines Steuer Elements an den Kanten von Formularen zur Entwurfszeit](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-134">[How to: Align a Control to the Edges of Forms at Design Time](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span></span>\
<span data-ttu-id="d0da9-135">Zeigt, wie Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft verwenden, um das Steuerelement an der Kante des Formulars auszurichten, das es einnimmt.</span><span class="sxs-lookup"><span data-stu-id="d0da9-135">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="d0da9-136">[Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>\
<span data-ttu-id="d0da9-137">Veranschaulicht das Verfahren, in dem das Steuerelement so installiert wird, dass es im Dialogfeld **Toolbox anpassen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-137">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>

<span data-ttu-id="d0da9-138">Gewusst [wie: Bereitstellen einer Toolbox Bitmap für ein Steuer](how-to-provide-a-toolbox-bitmap-for-a-control.md) Element</span><span class="sxs-lookup"><span data-stu-id="d0da9-138">[How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span></span>\
<span data-ttu-id="d0da9-139">Zeigt, wie die <xref:System.Drawing.ToolboxBitmapAttribute> verwendet wird, um ein Symbol neben dem benutzerdefinierten Steuerelement in der **Toolbox**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d0da9-139">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="d0da9-140">[Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-140">[How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span></span>\
<span data-ttu-id="d0da9-141">Veranschaulicht, wie der **UserControl-Testcontainer** verwendet wird, um das Verhalten eines zusammengesetzten Steuerelements zu testen.</span><span class="sxs-lookup"><span data-stu-id="d0da9-141">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>

<span data-ttu-id="d0da9-142">[Entwurfszeitfehler im Windows Forms-Designer](design-time-errors-in-the-windows-forms-designer.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-142">[Design-Time Errors in the Windows Forms Designer](design-time-errors-in-the-windows-forms-designer.md)</span></span>\
<span data-ttu-id="d0da9-143">Erläutert die Bedeutung und den Verwendungszweck der Entwurfszeitfehlerliste, die in Microsoft Visual Studio angezeigt wird, wenn der Windows Forms-Designer nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d0da9-143">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>

<span data-ttu-id="d0da9-144">[Problembehandlung beim Erstellen von Komponenten und Steuerelementen](troubleshooting-control-and-component-authoring.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-144">[Troubleshooting Control and Component Authoring](troubleshooting-control-and-component-authoring.md)</span></span>\
<span data-ttu-id="d0da9-145">Veranschaulicht, wie häufige Probleme diagnostiziert und behoben werden, die beim Erstellen einer benutzerdefinierten Komponente bzw. eines benutzerdefinierten Steuerelements auftreten können.</span><span class="sxs-lookup"><span data-stu-id="d0da9-145">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>

## <a name="reference"></a><span data-ttu-id="d0da9-146">Verweis</span><span class="sxs-lookup"><span data-stu-id="d0da9-146">Reference</span></span>

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a><span data-ttu-id="d0da9-147">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d0da9-147">Related sections</span></span>

<span data-ttu-id="d0da9-148">[Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-148">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="d0da9-149">Erörtert, wie Sie mit .NET Framework eigene benutzerdefinierte Steuerelemente erstellen können.</span><span class="sxs-lookup"><span data-stu-id="d0da9-149">Discusses how to create your own custom controls with the .NET Framework.</span></span>

<span data-ttu-id="d0da9-150">[Sprachunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-150">[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)</span></span>\
<span data-ttu-id="d0da9-151">Bietet eine Einführung in die Common Language Runtime, die zum Vereinfachen der Erstellung und Verwendung von Komponenten entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0da9-151">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="d0da9-152">Ein wichtiger Aspekt dieser Vereinfachung ist die verbesserte Interoperabilität zwischen Komponenten, die mit verschiedenen Programmiersprachen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="d0da9-152">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="d0da9-153">Durch die Common Language Specification (CLS) wird das Erstellen von Tools und Komponenten ermöglicht, die für mehrere Programmiersprachen ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="d0da9-153">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>

<span data-ttu-id="d0da9-154">[Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span><span class="sxs-lookup"><span data-stu-id="d0da9-154">[Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span></span>\
<span data-ttu-id="d0da9-155">Erläutert, wie Sie vorgehen müssen, damit eine Komponente oder ein Steuerelement im Dialogfeld **Toolbox anpassen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d0da9-155">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
