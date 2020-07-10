---
title: Überlagern von Objekten
description: Erfahren Sie, wie Sie Objekte auf Windows Forms Steuerelementen und untergeordneten Formularen Ebenen, um komplexere Benutzeroberflächen zu erstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6269b09c56963fefd500b9e1e6c9d7f51f9619cf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174509"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="5ff2d-103">Gewusst wie: Ebenenobjekte auf Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ff2d-103">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="5ff2d-104">Beim Erstellen einer komplexen Benutzeroberfläche oder bei Verwendung eines MDI-Formulars (Multiple Document Interface) empfiehlt es sich, sowohl Steuerelemente als auch untergeordnete Formulare zu verlagern, um komplexere Benutzeroberflächen (UI) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-104">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="5ff2d-105">Um Steuerelemente und Fenster innerhalb des Kontexts einer Gruppe zu verschieben und zu verfolgen, bearbeiten Sie Ihre *z-Reihenfolge*.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-105">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="5ff2d-106">Die z-Reihenfolge ist das visuelle Schichten von Steuerelementen in einem Formular entlang der z-Achse (Tiefe) des Formulars.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-106">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="5ff2d-107">Das Fenster oben in der z-Reihenfolge überlappt alle anderen Fenster.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-107">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="5ff2d-108">Alle anderen Fenster überlappen das Fenster am unteren Rand der z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-108">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="5ff2d-109">Auf ebenensteuerelemente zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="5ff2d-109">To layer controls at design time</span></span>

1. <span data-ttu-id="5ff2d-110">Wählen Sie in Visual Studio ein Steuerelement aus, das Sie Ebenen möchten.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-110">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="5ff2d-111">Wählen Sie im Menü **Format** die Option **Reihenfolge**aus, und wählen Sie dann **in den Vorder** Grund oder in den **Hintergrund**.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-111">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="5ff2d-112">Zum programmgesteuerten ebenensteuerelement</span><span class="sxs-lookup"><span data-stu-id="5ff2d-112">To layer controls programmatically</span></span>

<span data-ttu-id="5ff2d-113">Verwenden <xref:System.Windows.Forms.Control.BringToFront%2A> Sie die <xref:System.Windows.Forms.Control.SendToBack%2A> Methoden und, um die z-Reihenfolge der Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-113">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="5ff2d-114">Wenn sich z. b. ein <xref:System.Windows.Forms.TextBox> Steuerelement, `txtFirstName` , unter einem anderen Steuerelement befindet und Sie es oben verwenden möchten, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="5ff2d-114">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> <span data-ttu-id="5ff2d-115">Windows Forms unterstützt die Einschluss *Steuerung*.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-115">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="5ff2d-116">Die Einschluss Steuerung umfasst das Platzieren einer Reihe von Steuerelementen innerhalb eines enthaltenden Steuer Elements, z. b. eine Reihe von Steuer <xref:System.Windows.Forms.RadioButton> Elementen in einem <xref:System.Windows.Forms.GroupBox> Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ff2d-116">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="5ff2d-117">Anschließend können Sie die Steuerelemente innerhalb des enthaltenden Steuer Elements Schichten.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-117">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="5ff2d-118">Wenn Sie das Gruppenfeld verschieben, werden auch die Steuerelemente verschoben, da Sie darin enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5ff2d-118">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ff2d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ff2d-119">See also</span></span>

- [<span data-ttu-id="5ff2d-120">Windows Forms Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="5ff2d-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="5ff2d-121">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="5ff2d-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="5ff2d-122">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ff2d-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="5ff2d-123">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="5ff2d-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
