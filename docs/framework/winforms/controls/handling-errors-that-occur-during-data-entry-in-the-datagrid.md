---
title: 'Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten'
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
ms.openlocfilehash: cee6fe3b049378fa7bbe2585a3607049eaf231bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046076"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="be2de-102">Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten</span><span class="sxs-lookup"><span data-stu-id="be2de-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="be2de-103">Das Behandeln von Fehlern aus dem zugrunde liegenden Datenspeicher ist ein erforderliches Feature für eine Dateneingabe Anwendung.</span><span class="sxs-lookup"><span data-stu-id="be2de-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="be2de-104">Das Windows Forms <xref:System.Windows.Forms.DataGridView> -Steuerelement vereinfacht dies durch das <xref:System.Windows.Forms.DataGridView.DataError> verfügbar machen des-Ereignisses, das ausgelöst wird, wenn der Datenspeicher eine Einschränkungs Verletzung oder eine unterbrochene Geschäftsregel erkennt.</span><span class="sxs-lookup"><span data-stu-id="be2de-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="be2de-105">In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` -Tabelle in der Northwind-Beispieldatenbank ab und zeigen <xref:System.Windows.Forms.DataGridView> Sie in einem-Steuerelement an.</span><span class="sxs-lookup"><span data-stu-id="be2de-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="be2de-106">Wenn ein doppelter `CustomerID` Wert in einer neuen Zeile oder einer bearbeiteten vorhandenen Zeile erkannt wird, tritt <xref:System.Windows.Forms.DataGridView.DataError> das-Ereignis auf, das durch Anzeigen einer <xref:System.Windows.Forms.MessageBox> behandelt wird, die die Ausnahme beschreibt.</span><span class="sxs-lookup"><span data-stu-id="be2de-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="be2de-107">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)-Steuerelement auftreten.</span><span class="sxs-lookup"><span data-stu-id="be2de-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be2de-108">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="be2de-108">Prerequisites</span></span>

<span data-ttu-id="be2de-109">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="be2de-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="be2de-110">Zugriff auf einen Server mit der Beispieldatenbank Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="be2de-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="be2de-111">Erstellen des Formulars</span><span class="sxs-lookup"><span data-stu-id="be2de-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="be2de-112">So verarbeiten Sie Dateneingabe Fehler im DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="be2de-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="be2de-113">Erstellen Sie eine Klasse, die <xref:System.Windows.Forms.Form> von abgeleitet ist <xref:System.Windows.Forms.DataGridView> und ein- <xref:System.Windows.Forms.BindingSource> Steuerelement und eine-Komponente enthält.</span><span class="sxs-lookup"><span data-stu-id="be2de-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="be2de-114">Im folgenden Codebeispiel wird die grundlegende Initialisierung und `Main` eine-Methode bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="be2de-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="be2de-115">Implementieren Sie eine Methode in der Klassendefinition Ihres Formulars, um die Details der Verbindungs Herstellung mit der Datenbank zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="be2de-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="be2de-116">Dieses Codebeispiel verwendet eine `GetData` -Methode, die <xref:System.Data.DataTable> ein aufgefülltes Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="be2de-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="be2de-117">Stellen Sie sicher, dass Sie `connectionString` die Variable auf einen Wert festlegen, der für Ihre Datenbank geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="be2de-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="be2de-118">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="be2de-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="be2de-119">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="be2de-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="be2de-120">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="be2de-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="be2de-121">Implementieren Sie einen Handler für das- <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars, das <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> initialisiert, und richtet die Datenbindung ein.</span><span class="sxs-lookup"><span data-stu-id="be2de-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="be2de-122">Behandeln Sie <xref:System.Windows.Forms.DataGridView.DataError> das-Ereignis <xref:System.Windows.Forms.DataGridView>auf dem.</span><span class="sxs-lookup"><span data-stu-id="be2de-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="be2de-123">Wenn der Kontext für den Fehler ein Commitvorgang ist, wird der Fehler in einem <xref:System.Windows.Forms.MessageBox>angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be2de-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="be2de-124">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="be2de-124">Testing the Application</span></span>

<span data-ttu-id="be2de-125">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="be2de-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="be2de-126">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="be2de-126">To test the form</span></span>

- <span data-ttu-id="be2de-127">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="be2de-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="be2de-128">Sie sehen ein <xref:System.Windows.Forms.DataGridView> Steuerelement, das mit Daten aus der Customers-Tabelle gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="be2de-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="be2de-129">Wenn Sie einen doppelten Wert für `CustomerID` eingeben und den Bearbeitungs Commit durchführen, wird der Zellwert automatisch wieder hergestellt, und es wird ein <xref:System.Windows.Forms.MessageBox> angezeigt, in dem der Dateneingabe Fehler angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="be2de-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="be2de-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="be2de-130">Next Steps</span></span>

<span data-ttu-id="be2de-131">Diese Anwendung enthält grundlegende Kenntnisse über die <xref:System.Windows.Forms.DataGridView> Funktionen des-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="be2de-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="be2de-132">Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView> Steuer Elements auf verschiedene Weise anpassen:</span><span class="sxs-lookup"><span data-stu-id="be2de-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="be2de-133">Ändern von Rahmen-und Header Stilen.</span><span class="sxs-lookup"><span data-stu-id="be2de-133">Change border and header styles.</span></span> <span data-ttu-id="be2de-134">Weitere Informationen finden Sie unter [Vorgehensweise: Ändern Sie die Rahmen-und Rasterlinien Stile im Windows Forms DataGridView](change-the-border-and-gridline-styles-in-the-datagrid.md)-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="be2de-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="be2de-135">Aktivieren oder Einschränken der Benutzereingaben für <xref:System.Windows.Forms.DataGridView> das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="be2de-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="be2de-136">Weitere Informationen finden Sie unter [Vorgehensweise: Verhindern Sie das Hinzufügen und Löschen von Zeilen im Windows Forms DataGridView [-Steuer](prevent-row-addition-and-deletion-datagridview.md)Element, und Gewusst wie: Legen Sie die Spalten im Windows Forms DataGridView-Steuer](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Element als schreibgeschützt fest.</span><span class="sxs-lookup"><span data-stu-id="be2de-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="be2de-137">Überprüfen Sie die Benutzer <xref:System.Windows.Forms.DataGridView> Eingaben für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="be2de-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="be2de-138">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Validieren von Daten im Windows Forms DataGridView-](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="be2de-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="be2de-139">Verarbeiten Sie sehr große Datasets im virtuellen Modus.</span><span class="sxs-lookup"><span data-stu-id="be2de-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="be2de-140">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="be2de-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="be2de-141">Passen Sie die Darstellung von Zellen an.</span><span class="sxs-lookup"><span data-stu-id="be2de-141">Customize the appearance of cells.</span></span> <span data-ttu-id="be2de-142">Weitere Informationen finden Sie unter [Vorgehensweise: Passen Sie die Darstellung von Zellen im Windows Forms DataGridView-](customize-the-appearance-of-cells-in-the-datagrid.md) Steuer [Element an, und Gewusst wie: Legen Sie Standardzellen Stile für das Windows Forms DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)-Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="be2de-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="be2de-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be2de-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="be2de-144">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be2de-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="be2de-145">Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView-Steuerelement auftreten</span><span class="sxs-lookup"><span data-stu-id="be2de-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="be2de-146">Exemplarische Vorgehensweise: Validieren von Daten im Windows Forms DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="be2de-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="be2de-147">Protecting Connection Information (Schützen von Verbindungsinformationen)</span><span class="sxs-lookup"><span data-stu-id="be2de-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
