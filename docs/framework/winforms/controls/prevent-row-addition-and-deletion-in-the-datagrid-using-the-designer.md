---
title: Verhindern der Addition und Löschung von Zeilen im DataGridView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cc9aff0f15d1bd6de5c469ee7069a99f3360837a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728709"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="bed07-102">Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="bed07-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="bed07-103">Gelegentlich möchten Sie Benutzer daran hindern, neue Zeilen von Daten einzugeben oder vorhandene Zeilen in Ihrem <xref:System.Windows.Forms.DataGridView>-Steuerelement zu löschen.</span><span class="sxs-lookup"><span data-stu-id="bed07-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bed07-104">Neue Zeilen werden in der speziellen Zeile für neue Datensätze am unteren Rand des Steuer Elements eingegeben.</span><span class="sxs-lookup"><span data-stu-id="bed07-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="bed07-105">Wenn Sie die Zeilen Addition deaktivieren, wird die Zeile für neue Datensätze nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bed07-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="bed07-106">Sie können das Steuerelement dann vollständig schreibgeschützt machen, indem Sie Zeilen Löschung und Zellen Bearbeitung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bed07-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="bed07-107">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="bed07-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bed07-108">Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bed07-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="bed07-109">So verhindern Sie das Hinzufügen und Löschen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="bed07-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="bed07-110">Klicken Sie in der oberen rechten Ecke![](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")des Steuer Elements <xref:System.Windows.Forms.DataGridView> auf das Smarttagsymbol (Smarttagsymbol), und deaktivieren Sie dann die Kontrollkästchen **hinzufügen aktivieren** und **Löschen aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="bed07-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bed07-111">Deaktivieren Sie das Kontrollkästchen **Bearbeitung aktivieren** , damit das Steuerelement vollständig schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="bed07-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="bed07-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bed07-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bed07-113">Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="bed07-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="bed07-114">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bed07-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
