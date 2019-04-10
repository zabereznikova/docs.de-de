---
title: 'Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 2149cac7fb15052c2602ef20a6684696730aae1b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294465"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="8f70d-102">Vorgehensweise: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8f70d-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="8f70d-103">Können Sie den auflistungs-Editor, der die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement mit der Bezeichnung der **Spalten- und Zeilenstile** Dialogfeld, um die Zeilen und Spalten der Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f70d-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f70d-104">Wenn Sie ein Steuerelement, die mehrere Zeilen oder Spalten umfassen soll, legen die `RowSpan` und `ColumnSpan` Eigenschaften des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="8f70d-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="8f70d-105">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="8f70d-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="8f70d-106">Wenn Sie ein Steuerelement in einer Zelle ausrichten möchten oder wenn Sie ein Steuerelement in einer Zelle ausdehnen möchten, Verwenden des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f70d-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="8f70d-107">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="8f70d-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="8f70d-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="8f70d-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8f70d-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8f70d-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8f70d-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="8f70d-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="8f70d-111">Bearbeiten von Zeilen und Spalten</span><span class="sxs-lookup"><span data-stu-id="8f70d-111">To edit rows and columns</span></span>  
  
1. <span data-ttu-id="8f70d-112">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="8f70d-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2. <span data-ttu-id="8f70d-113">Klicken Sie auf die <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Zeilen und Spalten bearbeiten** zum Öffnen der  **Spalten- und Zeilenstile** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="8f70d-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="8f70d-114">Sie können auch der rechten Maustaste auf die <xref:System.Windows.Forms.TableLayoutPanel> steuern, und wählen Sie **Zeilen und Spalten bearbeiten** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="8f70d-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3. <span data-ttu-id="8f70d-115">Wählen Sie zum Hinzufügen oder Entfernen von Spalten, **Spalten** aus der **Elementtyp** im Dropdown Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="8f70d-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4. <span data-ttu-id="8f70d-116">Wählen Sie zum Hinzufügen oder Entfernen von Zeilen, **Zeilen** aus der **Elementtyp** im Dropdown Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="8f70d-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5. <span data-ttu-id="8f70d-117">Klicken Sie auf die **hinzufügen** Schaltfläche, um das Ende einer Zeile oder Spalte hinzufügen der **Member** Liste.</span><span class="sxs-lookup"><span data-stu-id="8f70d-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6. <span data-ttu-id="8f70d-118">Klicken Sie auf die **einfügen** , um eine Zeile oder Spalte, bevor Sie das aktuell ausgewählte Element in der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8f70d-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7. <span data-ttu-id="8f70d-119">Wenn Sie eine Zeile oder Spalte hinzufügen, wählen Sie die **Größentyp** für die neue Zeile oder Spalte.</span><span class="sxs-lookup"><span data-stu-id="8f70d-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="8f70d-120">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="8f70d-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8. <span data-ttu-id="8f70d-121">Um eine Zeile oder Spalte zu entfernen, klicken Sie auf die **entfernen** Schaltfläche, um das aktuell ausgewählte Element im Löschen der **Member** Liste.</span><span class="sxs-lookup"><span data-stu-id="8f70d-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f70d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f70d-122">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="8f70d-123">TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8f70d-123">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
