---
title: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 14dc1081a8608c6e6add67f641c4b55825d2fc81
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626970"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="02b26-102">Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="02b26-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="02b26-103">Beim Anzeigen von Daten, die in einem Windows Forms <xref:System.Windows.Forms.DataGridView>-Steuerelement angezeigt werden, möchten Benutzer mitunter die Werte in bestimmten Spalten vergleichen.</span><span class="sxs-lookup"><span data-stu-id="02b26-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="02b26-104">Dies kann unpraktisch sein, wenn die Spalten im Steuerelement weitgehend getrennt sind, insbesondere, wenn Benutzer einen Bildlauf nach oben und unten durchführen müssen, um alle gewünschten Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="02b26-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="02b26-105">Sie können die Aufgabe des Vergleichs von Spaltenwerten vereinfachen, indem Sie Ihren Benutzern ermöglichen, die Spalten neu zu ordnen.</span><span class="sxs-lookup"><span data-stu-id="02b26-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="02b26-106">Wenn Sie die Neuanordnung von Spalten aktivieren, können Benutzer eine Spalte an eine neue Position verschieben, indem Sie die Spalten Kopfzeile mit der Maus ziehen.</span><span class="sxs-lookup"><span data-stu-id="02b26-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="02b26-107">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="02b26-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="02b26-108">Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="02b26-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="02b26-109">So aktivieren Sie die Neuanordnung von Spalten</span><span class="sxs-lookup"><span data-stu-id="02b26-109">To enable column reordering</span></span>

- <span data-ttu-id="02b26-110">Klicken Sie in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>-Steuer Elements auf das Symbol "Designer Aktionen" (![kleinen schwarzen Pfeil](./media/designer-actions-glyph.gif)), und wählen Sie dann **Neuanordnung von Spalten aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="02b26-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="02b26-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02b26-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="02b26-112">Vorgehensweise: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="02b26-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="02b26-113">Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="02b26-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="02b26-114">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02b26-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
