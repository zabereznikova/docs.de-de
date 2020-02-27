---
title: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 2dd3f8bfcad39ca3d530c79a6e6a8170585f7adf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627954"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="90db7-102">Gewusst wie: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="90db7-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="90db7-103">Standardmäßig können Benutzer Text-und numerische Daten ändern, die im Windows Forms <xref:System.Windows.Forms.DataGridView>-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="90db7-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="90db7-104">Wenn Sie Daten anzeigen möchten, die nicht für Änderungen vorgesehen sind, müssen Sie die Spalten, die die Daten enthalten, als schreibgeschützt festlegen.</span><span class="sxs-lookup"><span data-stu-id="90db7-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="90db7-105">Informationen dazu, wie das Steuerelement vollständig schreibgeschützt wird, finden Sie unter Gewusst [wie: verhindern des Hinzufügens und Löschens von Zeilen im Windows Forms DataGridView-Steuerelement mithilfe des Designers](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="90db7-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="90db7-106">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="90db7-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="90db7-107">Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="90db7-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="90db7-108">So machen Sie eine Spalte mithilfe des Designers als schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="90db7-108">To make a column read-only by using the designer</span></span>

1. <span data-ttu-id="90db7-109">Klicken Sie in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>-Steuer Elements auf das Symbol für Designer Aktionen (![kleinen schwarzen Pfeil](./media/designer-actions-glyph.gif)), und wählen Sie dann **Spalten bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="90db7-109">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="90db7-110">Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="90db7-110">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="90db7-111">Legen Sie im Raster **Spalten Eigenschaften** die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>-Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="90db7-111">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90db7-112">Sie können eine Spalte auch als schreibgeschützt festlegen, wenn Sie Sie hinzufügen, **indem Sie im** Dialogfeld **Spalte hinzufügen** das Kontrollkästchen Schreibgeschützt aktivieren.</span><span class="sxs-lookup"><span data-stu-id="90db7-112">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="90db7-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90db7-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="90db7-114">Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="90db7-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="90db7-115">Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="90db7-115">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="90db7-116">Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="90db7-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="90db7-117">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90db7-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
