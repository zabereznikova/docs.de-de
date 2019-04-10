---
title: 'Vorgehensweise: Ändern der Reihenfolge von Spalten des DataGridView-Steuerelements in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: cb8aeb30e12f7af18b475fd7707fa9d2ede6a299
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311512"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="d6686-102">Vorgehensweise: Ändern der Reihenfolge von Spalten des DataGridView-Steuerelements in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="d6686-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="d6686-103">Wenn Sie ein Windows Forms binden <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer Datenquelle, die Anzeigereihenfolge von automatisch generierten Spalten hängt von der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="d6686-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="d6686-104">Wenn diese Reihenfolge nicht, was Sie bevorzugen ist, können Sie die Reihenfolge der Spalten mithilfe des Designers ändern.</span><span class="sxs-lookup"><span data-stu-id="d6686-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="d6686-105">Sie sollten auch das Steuerelement ungebundene Spalten hinzugefügt, und Ändern der angezeigten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="d6686-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="d6686-106">Informationen dazu, wie Sie programmgesteuert die Spaltenreihenfolge zu ändern, finden Sie unter [Vorgehensweise: Ändern Sie die Reihenfolge der Spalten im DataGridView-Steuerelement in Windows Forms](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d6686-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="d6686-107">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d6686-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d6686-108">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d6686-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6686-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="d6686-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d6686-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d6686-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d6686-111">Weitere Informationen finden Sie unter [Personalisieren der Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)</span><span class="sxs-lookup"><span data-stu-id="d6686-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)</span></span>  
  
### <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="d6686-112">So ändern Sie die Reihenfolge der Spalten mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="d6686-112">To change the column order using the designer</span></span>  
  
1. <span data-ttu-id="d6686-113">Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d6686-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2. <span data-ttu-id="d6686-114">Wählen Sie eine Spalte aus der **Selected Columns** Liste.</span><span class="sxs-lookup"><span data-stu-id="d6686-114">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="d6686-115">Klicken Sie auf den Pfeil nach oben oder nach-unten-Pfeil rechts neben der **ausgewählten Spalten** auflisten, bis die ausgewählte Spalte an der Position ist werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d6686-115">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6686-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6686-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d6686-117">Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="d6686-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="d6686-118">Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="d6686-118">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="d6686-119">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6686-119">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
