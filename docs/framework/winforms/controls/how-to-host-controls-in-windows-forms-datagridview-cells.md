---
title: 'Vorgehensweise: Hoststeuerelementen in Windows Forms-DataGridView-Zellen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 86a1577174c12e55b23dd8bce2cf00ac0e780abb
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261257"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="7872c-102">Vorgehensweise: Hoststeuerelementen in Windows Forms-DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="7872c-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="7872c-103">Das <xref:System.Windows.Forms.DataGridView>Steuerelement bietet mehrere Spaltentypen, die es den Benutzern ermöglichen, Werte auf vielfältige Weise einzugeben und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7872c-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="7872c-104">Wenn diese Spaltentypen Ihre Anforderungen an die Dateneingabe nicht erfüllen, können Sie jedoch auch eigene Spaltentypen mit Zellen erstellen, die von Ihnen gewählte Steuerelemente aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="7872c-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="7872c-105">Zu diesem Zweck müssen Sie Klassen definieren, die von <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.DataGridViewCell> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7872c-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="7872c-106">Außerdem müssen Sie eine Klasse definieren, die von <xref:System.Windows.Forms.Control> abgeleitet wird und die <xref:System.Windows.Forms.IDataGridViewEditingControl>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="7872c-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="7872c-107">Im folgenden Codebeispiel wird das Erstellen einer Kalenderspalte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7872c-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="7872c-108">Die Zellen dieser Spalte zeigen Daten in einfachen Textfeldzellen an. Wenn der Benutzer jedoch eine Zelle bearbeitet, wird ein <xref:System.Windows.Forms.DateTimePicker>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7872c-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="7872c-109">Um das erneute Implementieren der Funktionen für die Textfeldanzeige zu vermeiden, wird die `CalendarCell`Klasse von der <xref:System.Windows.Forms.DataGridViewTextBoxCell>-Klasse abgeleitet, anstatt die <xref:System.Windows.Forms.DataGridViewCell>-Klasse direkt zu erben.</span><span class="sxs-lookup"><span data-stu-id="7872c-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7872c-110">Wenn Sie von <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="7872c-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="7872c-111">Außerdem sollten Sie die `Clone`-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="7872c-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7872c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7872c-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7872c-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7872c-113">Compiling the Code</span></span>  
 <span data-ttu-id="7872c-114">Anforderungen für das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7872c-114">The following example requires:</span></span>  
  
-   <span data-ttu-id="7872c-115">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="7872c-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7872c-116">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7872c-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7872c-117">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="7872c-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7872c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7872c-118">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="7872c-119">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7872c-119">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7872c-120">Architektur des DataGridView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="7872c-120">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="7872c-121">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7872c-121">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
