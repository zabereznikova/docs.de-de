---
title: 'Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 12e6e15dd3b4e7941be198a526e8145ceb126e8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544613"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="6aaab-102">Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="6aaab-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="6aaab-103">In einigen Fällen wird der Datentyp einer Spalte ändern möchten, die bereits zu einem Windows Forms hinzugefügt wurde <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6aaab-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6aaab-104">Beispielsweise empfiehlt es sich um die Typen von einigen Spalten zu ändern, die automatisch generiert werden, wenn Sie das Steuerelement an eine Datenquelle binden.</span><span class="sxs-lookup"><span data-stu-id="6aaab-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="6aaab-105">Dies ist nützlich, wenn die Tabelle, die Sie anzeigen, Spalten, die Fremdschlüssel für Zeilen in einer verknüpften Tabelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="6aaab-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="6aaab-106">In diesem Fall empfiehlt es sich um die Textspalten für das Feld zu ersetzen, die diese Fremdschlüssel Spalten mit Kombinationsfeldern an, die mehr sinnvolle Werte aus der verknüpften Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6aaab-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="6aaab-107">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6aaab-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6aaab-108">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6aaab-108">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aaab-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="6aaab-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6aaab-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6aaab-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6aaab-111">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6aaab-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="6aaab-112">So ändern Sie den Datentyp einer Spalte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="6aaab-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="6aaab-113">Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6aaab-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="6aaab-114">Wählen Sie eine Spalte aus der **Selected Columns** Liste.</span><span class="sxs-lookup"><span data-stu-id="6aaab-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="6aaab-115">In der **Spalteneigenschaften** Raster legen die `ColumnType` Eigenschaft in den Spaltentyp der neuen.</span><span class="sxs-lookup"><span data-stu-id="6aaab-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aaab-116">Die `ColumnType` Eigenschaft ist eine Design-Time-only-Eigenschaft, die die Klasse, die den Spaltentyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="6aaab-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="6aaab-117">Es ist keiner vorhandenen Eigenschaft, die in einer Spaltenklasse definiert.</span><span class="sxs-lookup"><span data-stu-id="6aaab-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aaab-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6aaab-118">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="6aaab-119">Vorgehensweise: Create a New Windows Forms Application Project (Vorgehensweise: Erstellen Sie ein Windows-Anwendungsprojekt)</span><span class="sxs-lookup"><span data-stu-id="6aaab-119">How to: Create a Windows Application Project</span></span>](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)
- [<span data-ttu-id="6aaab-120">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6aaab-120">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
