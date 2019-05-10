---
title: Entwickeln eines zusammengesetzten Windows Forms-Steuerelements
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 2d6220a95d20cc0ab8ea1cdeb396804dfbcef8a1
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211475"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="28738-102">Entwickeln eines zusammengesetzten Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="28738-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="28738-103">Sie können ein zusammengesetztes Windows Forms-Steuerelement entwickeln, indem Sie andere Windows Forms-Steuerelemente kombinieren.</span><span class="sxs-lookup"><span data-stu-id="28738-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="28738-104">Zusammengesetzte Steuerelemente, die abgeleitet <xref:System.Web.UI.UserControl> werden als Benutzersteuerelemente bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="28738-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="28738-105">Die Basisklasse, <xref:System.Windows.Forms.UserControl>, ermöglicht Tastaturrouting für die untergeordneten Steuerelemente und stellt damit sicher, dass untergeordnete Steuerelemente den Fokus erhalten können.</span><span class="sxs-lookup"><span data-stu-id="28738-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="28738-106">Ein Beispiel für ein Benutzersteuerelement, finden Sie unter den <xref:System.Windows.Forms.UserControl> -Beispiel in [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="28738-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="28738-107">Der Windows Forms-Designer in Visual Studio stellt umfassende entwurfszeitunterstützung für die Erstellung von Benutzersteuerelementen bereit.</span><span class="sxs-lookup"><span data-stu-id="28738-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="28738-108">Vorgehensweise: Anzeigen eines Steuerelements in der Toolbox-Elemente-Dialogfeld "auswählen"</span><span class="sxs-lookup"><span data-stu-id="28738-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="28738-109">Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="28738-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="28738-110">Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit visuellen ElementC#</span><span class="sxs-lookup"><span data-stu-id="28738-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="28738-111">Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="28738-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="28738-112">Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="28738-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="28738-113">Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="28738-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="28738-114">Vorgehensweise: Erben von der Control-Klasse</span><span class="sxs-lookup"><span data-stu-id="28738-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="28738-115">Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl</span><span class="sxs-lookup"><span data-stu-id="28738-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="28738-116">Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="28738-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="28738-117">Vorgehensweise: Erben von der UserControl-Klasse</span><span class="sxs-lookup"><span data-stu-id="28738-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="28738-118">Vorgehensweise: Erstellen von Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="28738-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="28738-119">Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="28738-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="28738-120">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28738-120">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)

- [<span data-ttu-id="28738-121">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit visuellen ElementC#</span><span class="sxs-lookup"><span data-stu-id="28738-121">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="28738-122">Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28738-122">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)

- [<span data-ttu-id="28738-123">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das von Visual Studio-Entwurfszeitfunktionen nutzt</span><span class="sxs-lookup"><span data-stu-id="28738-123">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="28738-124">[Vorgehensweise: Erstellen Sie ein Windows Forms-Steuerelement, das Entwurfszeitfeatures nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="28738-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="28738-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28738-125">See also</span></span>

- [<span data-ttu-id="28738-126">Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="28738-126">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="28738-127">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="28738-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="28738-128">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="28738-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
