---
title: 'Gewusst wie: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75b83a2d7475f1a01d80c82013dac519edc4de08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="a8788-102">Gewusst wie: Bearbeiten von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a8788-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="a8788-103">Können Sie den auflistungs-Editor von der <xref:System.Windows.Forms.TableLayoutPanel> als Steuerelement der **Spalten- und Zeilenstile** (Dialogfeld), um die Zeilen und Spalten der Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a8788-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8788-104">Wenn Sie ein Steuerelement, die mehrere Zeilen oder Spalten umfassen soll, legen die `RowSpan` und `ColumnSpan` Eigenschaften des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="a8788-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="a8788-105">Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="a8788-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="a8788-106">Wenn Sie ein Steuerelement in einer Zelle ausrichten möchten, oder ein Steuerelement in einer Zelle gestreckt werden soll, verwenden Sie des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a8788-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="a8788-107">Weitere Informationen finden Sie unter [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="a8788-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="a8788-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="a8788-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a8788-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a8788-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a8788-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a8788-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="a8788-111">So bearbeiten Sie die Zeilen und Spalten</span><span class="sxs-lookup"><span data-stu-id="a8788-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="a8788-112">Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a8788-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="a8788-113">Klicken Sie auf die <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements Smarttag-Glyphe (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Zeilen und Spalten bearbeiten** So öffnen die  **Spalten- und Zeilenstile** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="a8788-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="a8788-114">Sie können auch mit der rechten Maustaste auf die <xref:System.Windows.Forms.TableLayoutPanel> steuern, und wählen Sie **Zeilen und Spalten bearbeiten** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="a8788-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="a8788-115">Wählen Sie zum Hinzufügen oder Entfernen von Spalten, **Spalten** aus der **Elementtyp** Dropdown Listenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="a8788-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="a8788-116">Wählen Sie zum Hinzufügen oder Entfernen von Zeilen, **Zeilen** aus der **Elementtyp** Dropdown Listenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="a8788-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="a8788-117">Klicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen einer Zeile oder Spalte an das Ende der **Member** Liste.</span><span class="sxs-lookup"><span data-stu-id="a8788-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="a8788-118">Klicken Sie auf die **einfügen** Schaltfläche, um eine Zeile oder Spalte vor dem aktuell ausgewählten Element in der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a8788-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="a8788-119">Wenn Sie eine Zeile oder Spalte hinzufügen, wählen Sie die **Größentyps** für die neue Zeile oder Spalte.</span><span class="sxs-lookup"><span data-stu-id="a8788-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="a8788-120">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="a8788-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="a8788-121">Um eine Zeile oder Spalte zu entfernen, klicken Sie auf die **entfernen** Schaltfläche, um das aktuell ausgewählte Element im Löschen der **Member** Liste.</span><span class="sxs-lookup"><span data-stu-id="a8788-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8788-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8788-122">See Also</span></span>  
 <xref:System.Windows.Forms.SizeType>  
 [<span data-ttu-id="a8788-123">TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a8788-123">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
