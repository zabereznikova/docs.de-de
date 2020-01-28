---
title: 'Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement auftreten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738735"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3f242-102">Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten</span><span class="sxs-lookup"><span data-stu-id="3f242-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="3f242-103">Das Behandeln von Fehlern aus dem zugrunde liegenden Datenspeicher ist ein erforderliches Feature für eine Dateneingabe Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3f242-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="3f242-104">Das Windows Forms <xref:System.Windows.Forms.DataGridView>-Steuerelement vereinfacht dies durch das verfügbar machen des <xref:System.Windows.Forms.DataGridView.DataError>-Ereignisses, das ausgelöst wird, wenn der Datenspeicher eine Einschränkungs Verletzung oder eine unterbrochene Geschäftsregel erkennt.</span><span class="sxs-lookup"><span data-stu-id="3f242-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="3f242-105">In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` Tabelle in der Northwind-Beispieldatenbank ab und zeigen Sie in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement an.</span><span class="sxs-lookup"><span data-stu-id="3f242-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3f242-106">Wenn ein doppelter `CustomerID` Wert in einer neuen Zeile oder einer bearbeiteten vorhandenen Zeile erkannt wird, tritt das <xref:System.Windows.Forms.DataGridView.DataError> Ereignis auf, das durch Anzeigen eines <xref:System.Windows.Forms.MessageBox> behandelt wird, das die Ausnahme beschreibt.</span><span class="sxs-lookup"><span data-stu-id="3f242-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="3f242-107">Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView-Steuerelement auftreten](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="3f242-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f242-108">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="3f242-108">Prerequisites</span></span>

<span data-ttu-id="3f242-109">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3f242-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="3f242-110">Zugriff auf einen Server mit der Beispieldatenbank Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3f242-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="3f242-111">Erstellen des Formulars</span><span class="sxs-lookup"><span data-stu-id="3f242-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="3f242-112">So verarbeiten Sie Dateneingabe Fehler im DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3f242-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="3f242-113">Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und ein <xref:System.Windows.Forms.DataGridView> Steuerelement und eine <xref:System.Windows.Forms.BindingSource> Komponente enthält.</span><span class="sxs-lookup"><span data-stu-id="3f242-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="3f242-114">Das folgende Codebeispiel stellt eine grundlegende Initialisierung bereit und enthält eine `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="3f242-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="3f242-115">Implementieren Sie eine Methode in der Klassendefinition Ihres Formulars, um die Details der Verbindungs Herstellung mit der Datenbank zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3f242-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="3f242-116">Dieses Codebeispiel verwendet eine `GetData`-Methode, die ein aufgefülltes <xref:System.Data.DataTable> Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f242-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="3f242-117">Stellen Sie sicher, dass Sie die `connectionString` Variable auf einen Wert festlegen, der für Ihre Datenbank geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="3f242-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3f242-118">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="3f242-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="3f242-119">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="3f242-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="3f242-120">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="3f242-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="3f242-121">Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars, das die <xref:System.Windows.Forms.DataGridView> initialisiert und <xref:System.Windows.Forms.BindingSource> und die Datenbindung einrichtet.</span><span class="sxs-lookup"><span data-stu-id="3f242-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="3f242-122">Behandeln Sie das <xref:System.Windows.Forms.DataGridView.DataError>-Ereignis auf dem <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="3f242-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="3f242-123">Wenn der Kontext für den Fehler ein Commitvorgang ist, wird der Fehler in einem <xref:System.Windows.Forms.MessageBox>angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f242-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="3f242-124">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="3f242-124">Testing the Application</span></span>

<span data-ttu-id="3f242-125">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="3f242-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="3f242-126">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="3f242-126">To test the form</span></span>

- <span data-ttu-id="3f242-127">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3f242-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="3f242-128">Sie sehen ein <xref:System.Windows.Forms.DataGridView>-Steuerelement, das mit Daten aus der Customers-Tabelle gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="3f242-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="3f242-129">Wenn Sie einen doppelten Wert für `CustomerID` eingeben und den Bearbeitungs Commit durchführen, wird der Zellwert automatisch wieder hergestellt, und es wird eine <xref:System.Windows.Forms.MessageBox> angezeigt, in der der Dateneingabe Fehler angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3f242-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3f242-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3f242-130">Next Steps</span></span>

<span data-ttu-id="3f242-131">Diese Anwendung bietet grundlegende Kenntnisse über die Funktionen des <xref:System.Windows.Forms.DataGridView>-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="3f242-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="3f242-132">Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView> Steuer Elements auf verschiedene Weise anpassen:</span><span class="sxs-lookup"><span data-stu-id="3f242-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="3f242-133">Ändern von Rahmen-und Header Stilen.</span><span class="sxs-lookup"><span data-stu-id="3f242-133">Change border and header styles.</span></span> <span data-ttu-id="3f242-134">Weitere Informationen finden Sie unter Gewusst [wie: Ändern der Rahmen-und Rasterlinien Stile im Windows Forms DataGridView-Steuer](change-the-border-and-gridline-styles-in-the-datagrid.md)Element.</span><span class="sxs-lookup"><span data-stu-id="3f242-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="3f242-135">Aktiviert oder schränkt die Benutzereingabe auf das <xref:System.Windows.Forms.DataGridView> Steuerelement ein.</span><span class="sxs-lookup"><span data-stu-id="3f242-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3f242-136">Weitere Informationen finden Sie unter Gewusst [wie: verhindern des Hinzufügens und Löschens von Zeilen im Windows Forms DataGridView-Steuer](prevent-row-addition-and-deletion-datagridview.md)Element und Gewusst wie: Festlegen von schreibgeschützten [Spalten im Windows Forms DataGridView-Steuer](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="3f242-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="3f242-137">Überprüfen Sie die Benutzereingaben für das <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3f242-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3f242-138">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Validieren von Daten im Windows Forms DataGridView-Steuer](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="3f242-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="3f242-139">Verarbeiten Sie sehr große Datasets im virtuellen Modus.</span><span class="sxs-lookup"><span data-stu-id="3f242-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="3f242-140">Weitere Informationen finden Sie unter Exemplarische [Vorgehensweise: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="3f242-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="3f242-141">Passen Sie die Darstellung von Zellen an.</span><span class="sxs-lookup"><span data-stu-id="3f242-141">Customize the appearance of cells.</span></span> <span data-ttu-id="3f242-142">Weitere Informationen finden Sie unter Gewusst [wie: Anpassen der Darstellung von Zellen im Windows Forms DataGridView-Steuer](customize-the-appearance-of-cells-in-the-datagrid.md) Element und Gewusst [wie: Festlegen von Standardzellen Formaten für das Windows Forms DataGridView-Steuer](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="3f242-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3f242-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f242-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="3f242-144">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f242-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3f242-145">Gewusst wie: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten</span><span class="sxs-lookup"><span data-stu-id="3f242-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="3f242-146">Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f242-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3f242-147">Protecting Connection Information (Schützen von Verbindungsinformationen)</span><span class="sxs-lookup"><span data-stu-id="3f242-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
