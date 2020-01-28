---
title: Ändern des Typs einer DataGridView-Spalte mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 976f257d38dc7be5c904e63da47c61486bd3301c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737136"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="2657f-102">Gewusst wie: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="2657f-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="2657f-103">Manchmal möchten Sie den Typ einer Spalte ändern, die bereits zu einem Windows Forms <xref:System.Windows.Forms.DataGridView>-Steuerelement hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="2657f-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2657f-104">Beispielsweise möchten Sie möglicherweise die Typen einiger Spalten ändern, die automatisch generiert werden, wenn Sie das Steuerelement an eine Datenquelle binden.</span><span class="sxs-lookup"><span data-stu-id="2657f-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="2657f-105">Dies ist nützlich, wenn in der angezeigten Tabelle Spalten mit Fremdschlüsseln für Zeilen in einer verknüpften Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2657f-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="2657f-106">In diesem Fall möchten Sie möglicherweise die Text Feld Spalten, in denen diese Fremdschlüssel angezeigt werden, durch Kombinations Feld-Spalten ersetzen, die aussagekräftige Werte aus der verknüpften Tabelle anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2657f-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>

 <span data-ttu-id="2657f-107">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="2657f-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2657f-108">Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="2657f-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="2657f-109">So ändern Sie den Typ einer Spalte mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="2657f-109">To change the type of a column using the designer</span></span>

1. <span data-ttu-id="2657f-110">Klicken Sie in der oberen rechten Ecke![](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")des Steuer Elements <xref:System.Windows.Forms.DataGridView> auf das Smarttagsymbol (Smarttagsymbol), und wählen Sie dann **Spalten bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="2657f-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="2657f-111">Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="2657f-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="2657f-112">Legen Sie im Raster **Spalten Eigenschaften** die `ColumnType`-Eigenschaft auf den neuen Spaltentyp fest.</span><span class="sxs-lookup"><span data-stu-id="2657f-112">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2657f-113">Die `ColumnType`-Eigenschaft ist eine reine Entwurfszeit Eigenschaft, die die Klasse angibt, die den Spaltentyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="2657f-113">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="2657f-114">Es handelt sich nicht um eine tatsächliche Eigenschaft, die in einer Spalten Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2657f-114">It is not an actual property defined in a column class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2657f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2657f-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="2657f-116">Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="2657f-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="2657f-117">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2657f-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
