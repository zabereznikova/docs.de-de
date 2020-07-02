---
title: 'Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement'
description: Erfahren Sie, wie Sie das Dialogfeld Spalten-und Zeilen Stile verwenden, um die Zeilen und Spalten der Windows Forms Steuerelemente zu bearbeiten.
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: cfd2ca4be5d5a2658a9a129d911f1dba9670ccfd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619350"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="67f0e-103">Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="67f0e-103">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="67f0e-104">Sie können den Auflistungs-Editor des- <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements, das als **Spalten-und Zeilen Stile** bezeichnet wird, verwenden, um die Zeilen und Spalten der Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="67f0e-104">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="67f0e-105">Wenn ein Steuerelement mehrere Zeilen oder Spalten umfassen soll, legen Sie die `RowSpan` -Eigenschaft und die-Eigenschaft `ColumnSpan` für das-Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="67f0e-105">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="67f0e-106">Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="67f0e-106">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="67f0e-107">Wenn Sie ein Steuerelement in einer Zelle ausrichten oder ein Steuerelement innerhalb einer Zelle Strecken möchten, verwenden Sie die-Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.Control.Anchor%2A> .</span><span class="sxs-lookup"><span data-stu-id="67f0e-107">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="67f0e-108">Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="67f0e-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="67f0e-109">So bearbeiten Sie Zeilen und Spalten</span><span class="sxs-lookup"><span data-stu-id="67f0e-109">To edit rows and columns</span></span>

1. <span data-ttu-id="67f0e-110">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="67f0e-110">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="67f0e-111">Klicken Sie auf das <xref:System.Windows.Forms.TableLayoutPanel> Designer-Aktions Symbol des Steuer Elements ( ![ kleiner schwarzer Pfeil ](./media/designer-actions-glyph.gif) ), und wählen Sie **Zeilen und Spalten bearbeiten** aus, um das Dialogfeld **Spalten-und Zeilen Stile** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67f0e-111">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="67f0e-112">Sie können auch mit der rechten Maustaste auf das Steuerelement klicken und im Kontext <xref:System.Windows.Forms.TableLayoutPanel> Menü **Zeilen und Spalten bearbeiten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="67f0e-112">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="67f0e-113">Wählen Sie zum Hinzufügen oder Entfernen von Spalten im Dropdown-Listenfeld **Elementtyp den Typ** **Spalten** aus.</span><span class="sxs-lookup"><span data-stu-id="67f0e-113">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="67f0e-114">Wählen Sie zum Hinzufügen oder Entfernen von Zeilen im Dropdown-Listenfeld **Elementtyp den Typ** **Zeilen** aus.</span><span class="sxs-lookup"><span data-stu-id="67f0e-114">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="67f0e-115">Klicken Sie auf die Schaltfläche **Hinzufügen** , um am **Ende der Elementliste eine** Zeile oder Spalte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="67f0e-115">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="67f0e-116">Klicken Sie auf die Schaltfläche **Einfügen** , um eine Zeile oder Spalte vor dem aktuell ausgewählten Element in der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="67f0e-116">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="67f0e-117">Wenn Sie eine Zeile oder Spalte hinzufügen, wählen Sie den **Größentyp** für die neue Zeile oder Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="67f0e-117">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="67f0e-118">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="67f0e-118">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="67f0e-119">Um eine Zeile oder Spalte zu entfernen, klicken Sie auf die Schaltfläche **Entfernen** , um das aktuell ausgewählte Element in der **Mitglieder** Liste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="67f0e-119">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="67f0e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67f0e-120">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="67f0e-121">TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="67f0e-121">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
