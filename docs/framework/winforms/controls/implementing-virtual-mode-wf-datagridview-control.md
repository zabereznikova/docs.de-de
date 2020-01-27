---
title: 'Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746518"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fdc85-102">Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdc85-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fdc85-103">Wenn Sie in einem <xref:System.Windows.Forms.DataGridView> Steuerelement sehr große Mengen an tabellarischen Daten anzeigen möchten, können Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft auf `true` festlegen und die Interaktion des Steuer Elements mit seinem Datenspeicher explizit verwalten.</span><span class="sxs-lookup"><span data-stu-id="fdc85-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="fdc85-104">Auf diese Weise können Sie die Leistung des Steuer Elements in dieser Situation optimieren.</span><span class="sxs-lookup"><span data-stu-id="fdc85-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="fdc85-105">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, um mit einem benutzerdefinierten Datenspeicher zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="fdc85-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="fdc85-106">Diese exemplarische Vorgehensweise führt Sie durch den Prozess der Implementierung dieser Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="fdc85-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="fdc85-107">Das Codebeispiel in diesem Thema verwendet zur Veranschaulichung eine sehr einfache Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="fdc85-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="fdc85-108">In einer Produktionseinstellung laden Sie in der Regel nur die Zeilen, die Sie in einem Cache anzeigen müssen, und behandeln <xref:System.Windows.Forms.DataGridView> Ereignisse, um mit dem Cache zu interagieren und ihn zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fdc85-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="fdc85-109">Weitere Informationen finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten in das Windows Forms DataGridView-Steuer](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md) Element.</span><span class="sxs-lookup"><span data-stu-id="fdc85-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="fdc85-110">Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="fdc85-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="fdc85-111">Erstellen des Formulars</span><span class="sxs-lookup"><span data-stu-id="fdc85-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="fdc85-112">So implementieren Sie den virtuellen Modus</span><span class="sxs-lookup"><span data-stu-id="fdc85-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="fdc85-113">Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und ein <xref:System.Windows.Forms.DataGridView> Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="fdc85-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="fdc85-114">Der folgende Code enthält eine grundlegende Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="fdc85-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="fdc85-115">Er deklariert einige Variablen, die in späteren Schritten verwendet werden, stellt eine `Main` Methode bereit und stellt ein einfaches Formularlayout im-Klassenkonstruktor bereit.</span><span class="sxs-lookup"><span data-stu-id="fdc85-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="fdc85-116">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars, das das <xref:System.Windows.Forms.DataGridView>-Steuerelement initialisiert und den Datenspeicher mit Beispiel Werten füllt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="fdc85-117">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignis, das den angeforderten Zellwert aus dem Datenspeicher abruft, oder das `Customer` Objekt, das gerade bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="fdc85-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="fdc85-118">Dieses Ereignis tritt auf, wenn das <xref:System.Windows.Forms.DataGridView>-Steuerelement eine Zelle zeichnen muss.</span><span class="sxs-lookup"><span data-stu-id="fdc85-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="fdc85-119">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValuePushed>-Ereignis, das einen bearbeiteten Zellwert im `Customer` Objekt speichert, das die bearbeitete Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="fdc85-120">Dieses Ereignis tritt auf, wenn der Benutzer eine Änderung eines Zellen Werts durchführt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="fdc85-121">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.NewRowNeeded>-Ereignis, das ein neues `Customer`-Objekt erstellt, das eine neu erstellte Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="fdc85-122">Dieses Ereignis tritt auf, wenn der Benutzer die Zeile für neue Datensätze eingibt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="fdc85-123">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowValidated>-Ereignis, das neue oder geänderte Zeilen im Datenspeicher speichert.</span><span class="sxs-lookup"><span data-stu-id="fdc85-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="fdc85-124">Dieses Ereignis tritt auf, wenn der Benutzer die aktuelle Zeile ändert.</span><span class="sxs-lookup"><span data-stu-id="fdc85-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="fdc85-125">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignis, das angibt, ob das <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis auftritt, wenn der Benutzer die Zeilen Neuversion durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus oder außerhalb des Bearbeitungsmodus signalisiert.</span><span class="sxs-lookup"><span data-stu-id="fdc85-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="fdc85-126">Standardmäßig erfolgt <xref:System.Windows.Forms.DataGridView.CancelRowEdit> bei der Zeilen Neuversion, wenn Zellen in der aktuellen Zeile geändert wurden, es sei denn, die <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>-Eigenschaft ist im <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignishandler auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="fdc85-127">Dieses Ereignis ist hilfreich, wenn der Commit-Bereich zur Laufzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="fdc85-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="fdc85-128">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis, das die Werte des `Customer` Objekts verwirft, das die aktuelle Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="fdc85-129">Dieses Ereignis tritt auf, wenn der Benutzer die Zeilen Neuversion durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus oder außerhalb des Bearbeitungsmodus signalisiert.</span><span class="sxs-lookup"><span data-stu-id="fdc85-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="fdc85-130">Dieses Ereignis tritt nicht auf, wenn keine Zellen in der aktuellen Zeile geändert wurden oder wenn der Wert der <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>-Eigenschaft auf `false` in einem <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>-Ereignishandler festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="fdc85-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="fdc85-131">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.UserDeletingRow> Ereignis, das ein vorhandenes `Customer` Objekt aus dem Datenspeicher löscht, oder verwirft ein nicht gespeichertes `Customer` Objekt, das eine neu erstellte Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="fdc85-132">Dieses Ereignis tritt auf, wenn der Benutzer eine Zeile durch Klicken auf einen Zeilen Header und durch Drücken der ENTF-Taste löscht.</span><span class="sxs-lookup"><span data-stu-id="fdc85-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="fdc85-133">Implementieren Sie eine einfache `Customers`-Klasse, die die Datenelemente darstellt, die in diesem Codebeispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fdc85-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="fdc85-134">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="fdc85-134">Testing the Application</span></span>  
 <span data-ttu-id="fdc85-135">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="fdc85-136">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="fdc85-136">To test the form</span></span>  
  
- <span data-ttu-id="fdc85-137">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="fdc85-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="fdc85-138">Es wird ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit drei Kundendatensätzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdc85-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="fdc85-139">Sie können die Werte mehrerer Zellen in einer Zeile ändern und die ESC-Taste zweimal im Bearbeitungsmodus drücken und einmal außerhalb des Bearbeitungsmodus, um die gesamte Zeile auf ihre ursprünglichen Werte zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="fdc85-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="fdc85-140">Wenn Sie Zeilen im Steuerelement ändern, hinzufügen oder löschen, werden `Customer` Objekte im Datenspeicher ebenfalls geändert, hinzugefügt oder gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fdc85-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fdc85-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fdc85-141">Next Steps</span></span>  
 <span data-ttu-id="fdc85-142">Diese Anwendung enthält grundlegende Kenntnisse über die Ereignisse, die Sie behandeln müssen, um den virtuellen Modus im <xref:System.Windows.Forms.DataGridView> Steuerelement zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="fdc85-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fdc85-143">Sie können diese grundlegende Anwendung auf verschiedene Arten verbessern:</span><span class="sxs-lookup"><span data-stu-id="fdc85-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="fdc85-144">Implementieren Sie einen Datenspeicher, der Werte aus einer externen Datenbank zwischenspeichert.</span><span class="sxs-lookup"><span data-stu-id="fdc85-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="fdc85-145">Der Cache sollte bei Bedarf Werte abrufen und verwerfen, sodass er nur die für die Anzeige erforderlichen Elemente enthält, während ein kleiner Speicherplatz auf dem Client Computer beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="fdc85-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="fdc85-146">Optimieren Sie die Leistung des Datenspeicher abhängig von Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="fdc85-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="fdc85-147">Beispielsweise möchten Sie möglicherweise langsame Netzwerkverbindungen anstelle der Arbeitsspeicher Beschränkungen von Client Computern kompensieren, indem Sie eine größere Cache Größe verwenden und die Anzahl der Datenbankabfragen minimieren.</span><span class="sxs-lookup"><span data-stu-id="fdc85-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="fdc85-148">Weitere Informationen zum Zwischenspeichern von Werten aus einer externen Datenbank finden [Sie unter Gewusst wie: Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten in das Windows Forms DataGridView-Steuer](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)Element.</span><span class="sxs-lookup"><span data-stu-id="fdc85-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc85-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdc85-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="fdc85-150">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdc85-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fdc85-151">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdc85-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fdc85-152">Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdc85-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="fdc85-153">Gewusst wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdc85-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
