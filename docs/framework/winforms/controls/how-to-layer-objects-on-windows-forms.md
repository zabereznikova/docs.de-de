---
title: Überlagern von Objekten
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
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736341"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="7a3f3-102">Gewusst wie: Ebenenobjekte auf Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a3f3-102">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="7a3f3-103">Beim Erstellen einer komplexen Benutzeroberfläche oder bei Verwendung eines MDI-Formulars (Multiple Document Interface) empfiehlt es sich, sowohl Steuerelemente als auch untergeordnete Formulare zu verlagern, um komplexere Benutzeroberflächen (UI) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="7a3f3-104">Um Steuerelemente und Fenster innerhalb des Kontexts einer Gruppe zu verschieben und zu verfolgen, bearbeiten Sie Ihre *z-Reihenfolge*.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-104">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="7a3f3-105">Die z-Reihenfolge ist das visuelle Schichten von Steuerelementen in einem Formular entlang der z-Achse (Tiefe) des Formulars.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-105">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="7a3f3-106">Das Fenster oben in der z-Reihenfolge überlappt alle anderen Fenster.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="7a3f3-107">Alle anderen Fenster überlappen das Fenster am unteren Rand der z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="7a3f3-108">Auf ebenensteuerelemente zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7a3f3-108">To layer controls at design time</span></span>

1. <span data-ttu-id="7a3f3-109">Wählen Sie in Visual Studio ein Steuerelement aus, das Sie Ebenen möchten.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-109">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="7a3f3-110">Wählen Sie im Menü **Format** die Option **Reihenfolge**aus, und wählen Sie dann **in den Vorder** Grund oder in den **Hintergrund**.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-110">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="7a3f3-111">Zum programmgesteuerten ebenensteuerelement</span><span class="sxs-lookup"><span data-stu-id="7a3f3-111">To layer controls programmatically</span></span>

<span data-ttu-id="7a3f3-112">Verwenden Sie die Methoden <xref:System.Windows.Forms.Control.BringToFront%2A> und <xref:System.Windows.Forms.Control.SendToBack%2A>, um die z-Reihenfolge der Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="7a3f3-113">Wenn sich z. b. ein <xref:System.Windows.Forms.TextBox> Steuerelement, `txtFirstName`, unter einem anderen Steuerelement befindet und Sie es oben verwenden möchten, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7a3f3-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

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
> <span data-ttu-id="7a3f3-114">Windows Forms unterstützt die Einschluss *Steuerung*.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="7a3f3-115">Die Kapselung von Steuerelementen umfasst das Platzieren einer Reihe von Steuerelementen innerhalb eines enthaltenden Steuer Elements, z. b. eine Reihe von <xref:System.Windows.Forms.RadioButton> Steuerelementen innerhalb <xref:System.Windows.Forms.GroupBox> eines</span><span class="sxs-lookup"><span data-stu-id="7a3f3-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="7a3f3-116">Anschließend können Sie die Steuerelemente innerhalb des enthaltenden Steuer Elements Schichten.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="7a3f3-117">Wenn Sie das Gruppenfeld verschieben, werden auch die Steuerelemente verschoben, da Sie darin enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7a3f3-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a3f3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a3f3-118">See also</span></span>

- [<span data-ttu-id="7a3f3-119">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="7a3f3-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="7a3f3-120">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="7a3f3-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="7a3f3-121">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="7a3f3-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="7a3f3-122">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="7a3f3-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
