---
title: Festlegen von abwechselnden Zeilen Stilen für das DataGridView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 74f65d03a359136de943f8a2937ed5e5f1e62519
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743047"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f380e-102">Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f380e-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="f380e-103">Tabellendaten werden häufig in einem Ledger-Format dargestellt, in dem abwechselnde Zeilen andere Hintergrundfarben aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f380e-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="f380e-104">Dieses Format erleichtert es dem Benutzer, zu erkennen, welche Zellen sich in jeder Zeile befinden, insbesondere bei breiten Tabellen mit vielen Spalten.</span><span class="sxs-lookup"><span data-stu-id="f380e-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="f380e-105">Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie vollständige Stilinformationen für abwechselnde Zeilen angeben.</span><span class="sxs-lookup"><span data-stu-id="f380e-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="f380e-106">Sie können Stilmerkmale wie Vordergrundfarbe und-Schriftart zusätzlich zur Hintergrundfarbe verwenden, um abwechselnde Zeilen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f380e-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="f380e-107">Weitere Informationen finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="f380e-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="f380e-108">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="f380e-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f380e-109">Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f380e-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="f380e-110">Definieren von Stilen für abwechselnde Zeilen</span><span class="sxs-lookup"><span data-stu-id="f380e-110">Define styles for alternating rows</span></span>

1. <span data-ttu-id="f380e-111">Wählen Sie im Designer das <xref:System.Windows.Forms.DataGridView>-Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="f380e-111">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="f380e-112">Klicken Sie im **Eigenschaften** Fenster auf die Schaltfläche mit den Auslassungs Punkten (![die Schaltfläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f380e-112">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="f380e-113">Definieren Sie im Dialogfeld **CellStyle Builder** den Stil durch Festlegen der Eigenschaften, und überprüfen Sie die Optionen im **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="f380e-113">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="f380e-114">Die Formate, die Sie angeben, werden für jede andere Zeile verwendet, die im Steuerelement angezeigt wird, beginnend mit dem zweiten.</span><span class="sxs-lookup"><span data-stu-id="f380e-114">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="f380e-115">Um Stile für die verbleibenden Zeilen zu definieren, wiederholen Sie die Schritte 2 und 3 mithilfe der <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f380e-115">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f380e-116">Zellen werden mithilfe von Stilen angezeigt, die von mehreren Eigenschaften geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="f380e-116">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="f380e-117">Weitere Informationen zur Stil Vererbung finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="f380e-117">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f380e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f380e-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="f380e-119">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f380e-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f380e-120">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f380e-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f380e-121">Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f380e-121">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f380e-122">Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="f380e-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="f380e-123">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f380e-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
