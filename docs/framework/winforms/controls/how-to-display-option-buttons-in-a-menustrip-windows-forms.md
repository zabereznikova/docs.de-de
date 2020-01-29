---
title: 'Gewusst wie: Anzeigen von Optionsfeldern in einem MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735529"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="08839-102">Gewusst wie: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="08839-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="08839-103">Options Felder, auch als Options Felder bezeichnet, ähneln Kontrollkästchen, mit dem Unterschied, dass Benutzer jeweils nur eine auswählen können.</span><span class="sxs-lookup"><span data-stu-id="08839-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="08839-104">Obwohl die <xref:System.Windows.Forms.ToolStripMenuItem>-Klasse standardmäßig kein Optionsfeld Verhalten bereitstellt, stellt die-Klasse ein Kontrollkästchen Verhalten bereit, das Sie anpassen können, um das Optionsfeld Verhalten für Menü Elemente in einem <xref:System.Windows.Forms.MenuStrip> Steuerelement zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="08839-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="08839-105">Wenn die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>-Eigenschaft eines Menü Elements `true`ist, können Benutzer auf das Element klicken, um die Anzeige eines Häkchens zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="08839-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="08839-106">Die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>-Eigenschaft gibt den aktuellen Zustand des Elements an.</span><span class="sxs-lookup"><span data-stu-id="08839-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="08839-107">Wenn Sie das grundlegende Optionsfeld Verhalten implementieren möchten, müssen Sie sicherstellen, dass die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>-Eigenschaft für das zuvor ausgewählte Element auf `false`festgelegt ist, wenn ein Element ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="08839-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="08839-108">In den folgenden Prozeduren wird beschrieben, wie diese und zusätzliche Funktionen in einer Klasse implementiert werden, die die <xref:System.Windows.Forms.ToolStripMenuItem> Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="08839-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="08839-109">Die `ToolStripRadioButtonMenuItem`-Klasse überschreibt Member wie <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> und <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>, um das Auswahl Verhalten und die Darstellung von Options Schaltflächen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="08839-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="08839-110">Darüber hinaus überschreibt diese Klasse die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>-Eigenschaft, sodass Optionen in einem Untermenü deaktiviert werden, es sei denn, das übergeordnete Element ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="08839-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="08839-111">So implementieren Sie das Auswahl Verhalten für die Options Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="08839-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="08839-112">Initialisieren Sie die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>-Eigenschaft, um `true`, um die Elementauswahl zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="08839-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="08839-113">Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A>-Methode, um die Auswahl des zuvor ausgewählten Elements zu löschen, wenn ein neues Element ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="08839-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="08839-114">Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A>-Methode, um sicherzustellen, dass das Klicken auf ein Element, das bereits ausgewählt wurde, die Auswahl nicht löscht.</span><span class="sxs-lookup"><span data-stu-id="08839-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="08839-115">So ändern Sie die Darstellung der Optionsfeld Elemente</span><span class="sxs-lookup"><span data-stu-id="08839-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="08839-116">Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>-Methode, um das Standard Häkchen durch ein Optionsfeld zu ersetzen, indem Sie die <xref:System.Windows.Forms.RadioButtonRenderer>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="08839-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="08839-117">Überschreiben Sie die Methoden <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>und <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A>, um den Zustand der Maus zu verfolgen und sicherzustellen, dass die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>-Methode den richtigen Optionsfeld Zustand zeichnet.</span><span class="sxs-lookup"><span data-stu-id="08839-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="08839-118">So deaktivieren Sie Optionen in einem Untermenü, wenn das übergeordnete Element nicht ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="08839-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="08839-119">Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>-Eigenschaft, sodass das Element deaktiviert ist, wenn es über ein übergeordnetes Element mit einem <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Wert von `true` und einem <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Wert `false`verfügt.</span><span class="sxs-lookup"><span data-stu-id="08839-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="08839-120">Überschreiben Sie die <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>-Methode, um das <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged>-Ereignis des übergeordneten Elements zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="08839-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="08839-121">Geben Sie im Handler für das übergeordnete Element <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> Ereignis das Element für die Aktualisierung der Anzeige mit dem neuen aktivierten Zustand ungültig.</span><span class="sxs-lookup"><span data-stu-id="08839-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="08839-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08839-122">Example</span></span>

<span data-ttu-id="08839-123">Das folgende Codebeispiel stellt die gesamte `ToolStripRadioButtonMenuItem`-Klasse sowie eine <xref:System.Windows.Forms.Form> Klasse und `Program`-Klasse bereit, um das Optionsfeld Verhalten zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="08839-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="08839-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="08839-124">Compiling the Code</span></span>

<span data-ttu-id="08839-125">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="08839-125">This example requires:</span></span>

- <span data-ttu-id="08839-126">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="08839-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="08839-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08839-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="08839-128">MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="08839-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="08839-129">Gewusst wie: Implementieren eines benutzerdefinierten ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="08839-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
