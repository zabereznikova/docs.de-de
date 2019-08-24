---
title: Entwickeln eines zusammengesetzten Windows Forms-Steuerelements
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 9ccbf3de3f5c65b99a06c29ffce4c96896d11fae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015956"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="fe72c-102">Entwickeln eines zusammengesetzten Windows Forms-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="fe72c-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="fe72c-103">Sie können ein zusammengesetztes Windows Forms-Steuerelement entwickeln, indem Sie andere Windows Forms-Steuerelemente kombinieren.</span><span class="sxs-lookup"><span data-stu-id="fe72c-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="fe72c-104">Zusammengesetzte Steuerelemente, <xref:System.Web.UI.UserControl> die von abgeleitet werden, sind Benutzer Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="fe72c-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="fe72c-105">Die Basisklasse, <xref:System.Windows.Forms.UserControl>, ermöglicht Tastaturrouting für die untergeordneten Steuerelemente und stellt damit sicher, dass untergeordnete Steuerelemente den Fokus erhalten können.</span><span class="sxs-lookup"><span data-stu-id="fe72c-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="fe72c-106">Ein Beispiel für ein Benutzer Steuerelement finden <xref:System.Windows.Forms.UserControl> Sie im Beispiel unter [Gewusst wie: Anwenden von Attributen in Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md)-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="fe72c-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="fe72c-107">Der Windows Forms-Designer in Visual Studio bietet umfangreiche Entwurfszeit Unterstützung für die Erstellung von Benutzer Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="fe72c-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="fe72c-108">Vorgehensweise: Anzeigen eines Steuer Elements im Dialog Feld "Toolbox Elemente auswählen"</span><span class="sxs-lookup"><span data-stu-id="fe72c-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="fe72c-109">Exemplarische Vorgehensweise: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="fe72c-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="fe72c-110">Exemplarische Vorgehensweise: Erben von einem Windows Forms-Steuerelement mit VisualC#</span><span class="sxs-lookup"><span data-stu-id="fe72c-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="fe72c-111">Vorgehensweise: Bereitstellen einer Toolbox Bitmap für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fe72c-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="fe72c-112">Vorgehensweise: Von vorhandenen Windows Forms Steuerelementen erben</span><span class="sxs-lookup"><span data-stu-id="fe72c-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="fe72c-113">Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fe72c-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="fe72c-114">Vorgehensweise: Erben von der Control-Klasse</span><span class="sxs-lookup"><span data-stu-id="fe72c-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="fe72c-115">Vorgehensweise: Testen des Lauf Zeit Verhaltens eines UserControl-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="fe72c-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="fe72c-116">Vorgehensweise: Ausrichten eines Steuer Elements an den Kanten von Formularen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fe72c-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="fe72c-117">Vorgehensweise: Erben von der UserControl-Klasse</span><span class="sxs-lookup"><span data-stu-id="fe72c-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="fe72c-118">Vorgehensweise: Steuerelemente für Windows Forms erstellen</span><span class="sxs-lookup"><span data-stu-id="fe72c-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="fe72c-119">Vorgehensweise: Zusammengesetzte Steuerelemente verfassen</span><span class="sxs-lookup"><span data-stu-id="fe72c-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="fe72c-120">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit VisualC#</span><span class="sxs-lookup"><span data-stu-id="fe72c-120">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="fe72c-121">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen nutzt</span><span class="sxs-lookup"><span data-stu-id="fe72c-121">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="fe72c-122">[Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das Entwurfszeit Features nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="fe72c-122">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="fe72c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe72c-123">See also</span></span>

- [<span data-ttu-id="fe72c-124">Vorgehensweise: Anwenden von Attributen in Windows Forms Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="fe72c-124">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="fe72c-125">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fe72c-125">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="fe72c-126">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="fe72c-126">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
