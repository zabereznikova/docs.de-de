---
title: 'Vorgehensweise: Sicherstellen, dass die ausgewählte Zeile in einer untergeordneten Tabelle an der richtigen Position verbleibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
ms.openlocfilehash: 891a9a4d092de35ceff2f5ceb6dbde77cf2ca2ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966953"
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a><span data-ttu-id="30a4b-102">Vorgehensweise: Sicherstellen, dass die ausgewählte Zeile in einer untergeordneten Tabelle an der richtigen Position verbleibt</span><span class="sxs-lookup"><span data-stu-id="30a4b-102">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>
<span data-ttu-id="30a4b-103">Wenn Sie mit Datenbindungen in Windows Forms arbeiten, zeigen Sie diese Daten häufig in einer so genannten hierarchischen oder Master-/Detail-Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="30a4b-103">Oftentimes when you work with data binding in Windows Forms, you will display data in what is called a parent/child or master/details view.</span></span> <span data-ttu-id="30a4b-104">Diese Bezeichnung bezieht sich auf ein Datenbindungsszenario, bei dem Daten aus der gleichen Quelle in zwei Steuerelementen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="30a4b-104">This refers to a data-binding scenario where data from the same source is displayed in two controls.</span></span> <span data-ttu-id="30a4b-105">Wird die Auswahl in einem Steuerelement geändert, ändern sich die Daten, die im zweiten Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="30a4b-105">Changing the selection in one control causes the data displayed in the second control to change.</span></span> <span data-ttu-id="30a4b-106">So enthält das erste Steuerelement möglicherweise eine Kundenliste, und im zweiten Steuerelement wird eine Liste der Bestellungen angezeigt, die der im ersten Steuerelement ausgewählte Kunde getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="30a4b-106">For example, the first control might contain a list of customers and the second a list of orders related to the selected customer in the first control.</span></span>  
  
 <span data-ttu-id="30a4b-107">Beginnend mit .NET Framework, Version 2.0, müssen Sie beim Anzeigen von Daten in einer hierarchischen Ansicht möglicherweise zusätzliche Schritte unternehmen, um sicherzustellen, dass die aktuell in der untergeordneten Tabelle ausgewählte Zeile nicht auf die erste Zeile der Tabelle zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="30a4b-107">Starting with the .NET Framework version 2.0, when you display data in a parent/child view you might have to take extra steps to make sure that the currently selected row in the child table is not reset to the first row of the table.</span></span> <span data-ttu-id="30a4b-108">Hierfür müssen Sie die Position in der untergeordneten Tabelle zwischenspeichern und zurücksetzen, nachdem die übergeordnete Tabelle geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="30a4b-108">In order to do this, you will have to cache the child table position and reset it after the parent table changes.</span></span> <span data-ttu-id="30a4b-109">Normalerweise erfolgt das Zurücksetzen der untergeordneten Tabelle zum ersten Mal, wenn ein Feld in einer Zeile der übergeordneten Tabelle geändert wird.</span><span class="sxs-lookup"><span data-stu-id="30a4b-109">Typically the child reset occurs the first time a field in a row of the parent table changes.</span></span>  
  
### <a name="to-cache-the-current-child-position"></a><span data-ttu-id="30a4b-110">So speichern Sie die aktuelle untergeordnete Position zwischen</span><span class="sxs-lookup"><span data-stu-id="30a4b-110">To Cache the Current Child Position</span></span>  
  
1. <span data-ttu-id="30a4b-111">Deklarieren Sie eine ganzzahlige Variable zum Speichern der Position in der untergeordneten Liste und eine boolesche Variable, um zu speichern, ob die untergeordnete Position zwischengespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="30a4b-111">Declare an integer variable to store the child list position and a Boolean variable to store whether to cache the child position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2. <span data-ttu-id="30a4b-112">Behandeln Sie das <xref:System.Windows.Forms.CurrencyManager.ListChanged>-Ereignis für den <xref:System.Windows.Forms.CurrencyManager> der Bindung, und prüfen Sie auf einen <xref:System.ComponentModel.ListChangedType> von <xref:System.ComponentModel.ListChangedType.Reset>.</span><span class="sxs-lookup"><span data-stu-id="30a4b-112">Handle the <xref:System.Windows.Forms.CurrencyManager.ListChanged> event for the binding's <xref:System.Windows.Forms.CurrencyManager> and check for a <xref:System.ComponentModel.ListChangedType> of <xref:System.ComponentModel.ListChangedType.Reset>.</span></span>  
  
3. <span data-ttu-id="30a4b-113">Überprüfen Sie die aktuelle Position von <xref:System.Windows.Forms.CurrencyManager>.</span><span class="sxs-lookup"><span data-stu-id="30a4b-113">Check the current position of the <xref:System.Windows.Forms.CurrencyManager>.</span></span> <span data-ttu-id="30a4b-114">Ist diese größer als der erste Eintrag in der Liste (normalerweise 0), speichern Sie sie in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="30a4b-114">If it is greater than first entry in the list (typically 0), save it to a variable.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="30a4b-115">Behandeln Sie das <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>-Ereignis für den übergeordneten Währungs-Manager der übergeordneten Liste.</span><span class="sxs-lookup"><span data-stu-id="30a4b-115">Handle the parent list's <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> event for the parent currency manager.</span></span> <span data-ttu-id="30a4b-116">Legen Sie im Handler den booleschen Wert fest, um anzugeben, dass es sich nicht um ein Zwischenspeicherungsszenario handelt.</span><span class="sxs-lookup"><span data-stu-id="30a4b-116">In the handler, set the Boolean value to indicate it is not a caching scenario.</span></span> <span data-ttu-id="30a4b-117">Wenn <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> auftritt, handelt es sich bei der Änderung an der übergeordneten Liste um eine Positionsänderung und nicht um eine Änderung des Elementwerts.</span><span class="sxs-lookup"><span data-stu-id="30a4b-117">If the <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> occurs, the change to the parent is a list position change and not an item value change.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a><span data-ttu-id="30a4b-118">So setzen Sie die untergeordnete Position zurück</span><span class="sxs-lookup"><span data-stu-id="30a4b-118">To Reset the Child Position</span></span>  
  
1. <span data-ttu-id="30a4b-119">Behandeln Sie das <xref:System.Windows.Forms.BindingManagerBase.PositionChanged>-Ereignis für den <xref:System.Windows.Forms.CurrencyManager> der Bindung der untergeordneten Liste.</span><span class="sxs-lookup"><span data-stu-id="30a4b-119">Handle the <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> event for the child binding's <xref:System.Windows.Forms.CurrencyManager>.</span></span>  
  
2. <span data-ttu-id="30a4b-120">Setzen Sie die Position in der untergeordneten Tabelle auf die zwischengespeicherte Position zurück, die mit der vorherigen Prozedur gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="30a4b-120">Reset the child table position to the cached position saved in the previous procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="30a4b-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30a4b-121">Example</span></span>  
 <span data-ttu-id="30a4b-122">Das folgende Beispiel zeigt, wie die aktuelle Position von <xref:System.Windows.Forms.CurrencyManager> für eine untergeordnete Tabelle gespeichert und dann zurückgesetzt wird, nachdem die Bearbeitung der übergeordneten Tabelle abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="30a4b-122">The following example demonstrates how to save the current position on the <xref:System.Windows.Forms.CurrencyManager>.for a child table and reset the position after an edit is completed on the parent table.</span></span> <span data-ttu-id="30a4b-123">Das Beispiel enthält zwei <xref:System.Windows.Forms.DataGridView>-Steuerelemente, die mit einer <xref:System.Windows.Forms.BindingSource>-Komponente an zwei Tabellen in einem <xref:System.Data.DataSet> gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="30a4b-123">This example contains two <xref:System.Windows.Forms.DataGridView> controls bound to two tables in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="30a4b-124">Zwischen den beiden Tabellen wird eine Beziehung hergestellt, und diese Beziehung wird zu <xref:System.Data.DataSet> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="30a4b-124">A relation is established between the two tables and the relation is added to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="30a4b-125">Die Position in der untergeordneten Tabelle wird zu Demonstrationszwecken anfänglich auf die dritte Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="30a4b-125">The position in the child table is initially set to the third row for demonstration purposes.</span></span>  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 <span data-ttu-id="30a4b-126">Führen Sie die folgenden Schritte aus, um das Codebeispiel zu testen:</span><span class="sxs-lookup"><span data-stu-id="30a4b-126">To test the code example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="30a4b-127">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="30a4b-127">Run the example.</span></span>  
  
2. <span data-ttu-id="30a4b-128">Vergewissern Sie sich, dass das Kontrollkästchen **Position zwischenspeichern und zurücksetzen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="30a4b-128">Make sure the **Cache and reset position** check box is selected.</span></span>  
  
3. <span data-ttu-id="30a4b-129">Klicken Sie auf die Schaltfläche **Übergeordnetes Feld löschen**, um eine Änderung an einem Feld der übergeordneten Tabelle zu veranlassen.</span><span class="sxs-lookup"><span data-stu-id="30a4b-129">Click the **Clear parent field** button to cause a change in a field of the parent table.</span></span> <span data-ttu-id="30a4b-130">Beachten Sie, dass sich die ausgewählte Zeile in der untergeordneten Tabelle nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="30a4b-130">Notice that the selected row in the child table does not change.</span></span>  
  
4. <span data-ttu-id="30a4b-131">Schließen Sie das Beispiel, und führen Sie es erneut aus.</span><span class="sxs-lookup"><span data-stu-id="30a4b-131">Close and run the example again.</span></span> <span data-ttu-id="30a4b-132">Dies ist erforderlich, da die Rücksetzung erst nach der ersten Änderung in der übergeordneten Zeile stattfindet.</span><span class="sxs-lookup"><span data-stu-id="30a4b-132">You need to do this because the reset behavior occurs only on the first change in the parent row.</span></span>  
  
5. <span data-ttu-id="30a4b-133">Deaktivieren Sie das Kontrollkästchen **Position zwischenspeichern und zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="30a4b-133">Clear the **Cache and reset position** check box.</span></span>  
  
6. <span data-ttu-id="30a4b-134">Klicken Sie auf die Schaltfläche **Übergeordnetes Feld löschen**.</span><span class="sxs-lookup"><span data-stu-id="30a4b-134">Click the **Clear parent field** button.</span></span> <span data-ttu-id="30a4b-135">Beachten Sie, dass sich die ausgewählte Zeile in der untergeordneten Tabelle nun auf die erste Zeile ändert.</span><span class="sxs-lookup"><span data-stu-id="30a4b-135">Notice that the selected row in the child table changes to the first row.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30a4b-136">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="30a4b-136">Compiling the Code</span></span>  
 <span data-ttu-id="30a4b-137">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="30a4b-137">This example requires:</span></span>  
  
- <span data-ttu-id="30a4b-138">Verweise auf die Assemblys "System", "System.Data", "System.Drawing", "System.Windows.Forms" und "System.XML".</span><span class="sxs-lookup"><span data-stu-id="30a4b-138">References to the System, System.Data, System.Drawing, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="30a4b-139">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual C#-, finden Sie unter [erstellen über die Befehlszeile](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [mit csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="30a4b-139">For information about how to build this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="30a4b-140">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="30a4b-140">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a4b-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30a4b-141">See also</span></span>

- [<span data-ttu-id="30a4b-142">Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben</span><span class="sxs-lookup"><span data-stu-id="30a4b-142">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)
- [<span data-ttu-id="30a4b-143">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="30a4b-143">BindingSource Component</span></span>](./controls/bindingsource-component.md)
- [<span data-ttu-id="30a4b-144">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30a4b-144">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
