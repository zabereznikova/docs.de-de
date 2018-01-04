---
title: 'Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b9a70aaf2643811354cc9d7f6b51ed0805ca916
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3f8ff-102">Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f8ff-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3f8ff-103">Wenn sehr große Mengen von Tabellendaten in angezeigt werden soll eine <xref:System.Windows.Forms.DataGridView> -Steuerelements legen Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und das Steuerelement Interaktion mit dem Datenspeicher explizit verwalten.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="3f8ff-104">So können Sie beim Optimieren der Leistung des Steuerelements in dieser Situation.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="3f8ff-105">Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, um einen benutzerdefinierten Datenspeicher interagieren.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="3f8ff-106">Diese exemplarische Vorgehensweise führt Sie durch den Prozess der Implementierung dieser Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="3f8ff-107">Das Codebeispiel in diesem Thema wird eine sehr einfache Datenquelle zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="3f8ff-108">In einer produktionsumgebung, in der Regel nur die Zeilen, die Sie in den Cache anzuzeigen und zu behandeln müssen laden <xref:System.Windows.Forms.DataGridView> Ereignisse zur Interaktion und zum Aktualisieren des Caches.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="3f8ff-109">Weitere Informationen finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="3f8ff-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="3f8ff-110">Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="3f8ff-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="3f8ff-111">Erstellen des Formulars</span><span class="sxs-lookup"><span data-stu-id="3f8ff-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="3f8ff-112">Zum Implementieren virtuellen Modus</span><span class="sxs-lookup"><span data-stu-id="3f8ff-112">To implement virtual mode</span></span>  
  
1.  <span data-ttu-id="3f8ff-113">Erstellen Sie eine Klasse, die abgeleitet <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="3f8ff-114">Der folgende Code enthält einige grundlegende Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="3f8ff-115">Es einige Variablen deklariert, die in späteren Schritten verwendet werden, bietet eine `Main` -Methode, und bietet ein einfaches Formularlayout im Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  <span data-ttu-id="3f8ff-116">Implementieren Sie einen Handler für Ihr Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> steuern und der Datenspeicher mit Beispieldaten gefüllt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  <span data-ttu-id="3f8ff-117">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignis, das den angeforderten Zellenwert aus dem Datenspeicher abruft oder die `Customer` Objekt derzeit in Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="3f8ff-118">Dieses Ereignis tritt auf, wenn die <xref:System.Windows.Forms.DataGridView> Steuerelement eine Zelle gezeichnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  <span data-ttu-id="3f8ff-119">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValuePushed> Ereignis, das einen bearbeitete Zellenwert in speichert die `Customer` Objekt, das die bearbeitete Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="3f8ff-120">Dieses Ereignis tritt auf, wenn der Benutzer eine Änderung in der Zelle Wert ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  <span data-ttu-id="3f8ff-121">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.NewRowNeeded> Ereignis, das eine neue erstellt `Customer` Objekt, das eine neu erstellte Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="3f8ff-122">Dieses Ereignis tritt auf, wenn der Benutzer die Zeile für neue Datensätze eingibt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  <span data-ttu-id="3f8ff-123">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowValidated> Ereignis, das neue oder geänderte Zeilen im Datenspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="3f8ff-124">Dieses Ereignis tritt auf, wenn der Benutzer die aktuelle Zeile ändert.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  <span data-ttu-id="3f8ff-125">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignis, das angibt, ob die <xref:System.Windows.Forms.DataGridView.CancelRowEdit> -Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken von ESC zweimal im Bearbeitungsmodus befindet oder einmal außerhalb Bearbeitungsmodus signalisiert.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="3f8ff-126">Standardmäßig <xref:System.Windows.Forms.DataGridView.CancelRowEdit> beim Zurücksetzen von Zeilen tritt auf, wenn keine Zellen in der aktuellen Zeile geändert wurden, sofern die <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> -Eigenschaftensatz auf `true` in der <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="3f8ff-127">Dieses Ereignis ist nützlich, wenn der Commit-Bereich zur Laufzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  <span data-ttu-id="3f8ff-128">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis, das die Werte der verwirft die `Customer` Objekt, das die aktuelle Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="3f8ff-129">Dieses Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken von ESC zweimal im Bearbeitungsmodus befindet oder einmal außerhalb Bearbeitungsmodus signalisiert.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="3f8ff-130">Dieses Ereignis tritt nicht auf, wenn keine Zellen in der aktuellen Zeile geändert wurden oder wenn der Wert des der <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> Eigenschaft auf festgelegt wurde `false` in einen <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="3f8ff-131">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.UserDeletingRow> Ereignis, das ein vorhandenes löscht `Customer` Objekt aus dem Datenspeicher zusammen oder verwirft eine ungespeicherte `Customer` Objekt, das eine neu erstellte Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="3f8ff-132">Dieses Ereignis tritt auf, wenn der Benutzer eine Zeile gelöscht wird, indem Sie auf einen Zeilenkopf, und drücken die ENTF-Taste.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="3f8ff-133">Implementieren Sie eine einfache `Customers` Klasse, um die Datenelemente, die von diesem Codebeispiel verwendeten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="3f8ff-134">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="3f8ff-134">Testing the Application</span></span>  
 <span data-ttu-id="3f8ff-135">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="3f8ff-136">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="3f8ff-136">To test the form</span></span>  
  
-   <span data-ttu-id="3f8ff-137">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="3f8ff-138">Sehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit drei Kundendatensätze aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="3f8ff-139">Sie können ändern Sie die Werte aus mehreren Zellen in einer Zeile, und drücken Sie ESC, zweimal im Bearbeitungsmodus befindet und einmal außerhalb Bearbeitungsmodus wechseln, um die gesamte Zeile auf die ursprünglichen Werte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="3f8ff-140">Wenn Sie ändern, hinzufügen oder Löschen von Zeilen im Steuerelement `Customer` Objekte im Datenspeicher geändert, hinzugefügt oder ebenfalls gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3f8ff-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3f8ff-141">Next Steps</span></span>  
 <span data-ttu-id="3f8ff-142">Diese Anwendung bietet Ihnen ein grundlegendes Verständnis der Ereignisse müssen Sie zum Implementieren des virtuellen Modus im behandeln die <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3f8ff-143">Sie können diese grundlegenden Anwendung auf vielfältige Weise verbessern:</span><span class="sxs-lookup"><span data-stu-id="3f8ff-143">You can improve this basic application in a number of ways:</span></span>  
  
-   <span data-ttu-id="3f8ff-144">Implementieren Sie einen Datenspeicher, der Werte aus einer externen Datenbank zwischenspeichert.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="3f8ff-145">Der Cache sollte abrufen und Werte nach Bedarf zu verwerfen, sodass sie nur enthält, was für die Anzeige Anspruch eine kleine Menge an Arbeitsspeicher auf dem Clientcomputer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
-   <span data-ttu-id="3f8ff-146">Optimieren der Leistung des Datenspeichers je nach Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="3f8ff-147">Sie möchten z. B. mithilfe von Cache zu einem größeren und Minimieren der Anzahl der Datenbankabfragen für langsame Verbindungen anstelle der Clientcomputer Memory-Einschränkungen zu kompensieren.</span><span class="sxs-lookup"><span data-stu-id="3f8ff-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="3f8ff-148">Weitere Informationen zum Zwischenspeichern von Werten aus einer externen Datenbank finden Sie unter [wie: Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="3f8ff-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8ff-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f8ff-149">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [<span data-ttu-id="3f8ff-150">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f8ff-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="3f8ff-151">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f8ff-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="3f8ff-152">Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f8ff-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="3f8ff-153">Gewusst wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f8ff-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
