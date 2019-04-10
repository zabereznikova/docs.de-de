---
title: 'Vorgehensweise: Binden von Daten an das MaskedTextBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
ms.openlocfilehash: ebc8eaf63c6b5280961a80ef11afb919810dbdb8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342231"
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="b55b3-102">Vorgehensweise: Binden von Daten an das MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b55b3-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="b55b3-103">Binden von Daten an eine <xref:System.Windows.Forms.MaskedTextBox> genauso wie jedes andere Windows Forms-Steuerelement zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b55b3-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="b55b3-104">Wenn das Format der Daten in der Datenbank nicht das erwartete durch Ihre Maskendefinition Format übereinstimmt, müssen Sie jedoch die Daten neu zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="b55b3-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="b55b3-105">Das folgende Verfahren veranschaulicht, wie dieses Vorgangs unter Verwendung der <xref:System.Windows.Forms.Binding.Format> und <xref:System.Windows.Forms.Binding.Parse> Ereignisse der <xref:System.Windows.Forms.Binding> Klasse, um separate Telefonnummer anzeigen und phone Erweiterungsfelder für die Datenbank als einzelnes Feld bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b55b3-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="b55b3-106">Das folgende Verfahren ist erforderlich, dass Sie Zugriff auf SQL Server-Datenbank mit der Northwind-Beispieldatenbank installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b55b3-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="b55b3-107">So binden Sie Daten an eine MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b55b3-107">To bind data to a MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="b55b3-108">Erstellen Sie ein neues Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="b55b3-108">Create a new Windows Forms project.</span></span>  
  
2. <span data-ttu-id="b55b3-109">Ziehen Sie zwei <xref:System.Windows.Forms.TextBox> Steuerelemente auf das Formular aus, nennen Sie diese `FirstName` und `LastName`.</span><span class="sxs-lookup"><span data-stu-id="b55b3-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3. <span data-ttu-id="b55b3-110">Ziehen Sie eine <xref:System.Windows.Forms.MaskedTextBox> steuern, auf das Formular, nennen Sie sie `PhoneMask`.</span><span class="sxs-lookup"><span data-stu-id="b55b3-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4. <span data-ttu-id="b55b3-111">Legen Sie die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft `PhoneMask` zu `(000) 000-0000 x9999`.</span><span class="sxs-lookup"><span data-stu-id="b55b3-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5. <span data-ttu-id="b55b3-112">Fügen Sie, dass die folgenden Namespaceimporte auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="b55b3-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6. <span data-ttu-id="b55b3-113">Mit der rechten Maustaste in des Formulars, und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="b55b3-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="b55b3-114">Platzieren Sie diesen Code an einer beliebigen Stelle in der Form-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b55b3-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the   
        // initial load.   
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the   
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7. <span data-ttu-id="b55b3-115">Fügen Sie Ereignishandler für die <xref:System.Windows.Forms.Binding.Format> und <xref:System.Windows.Forms.Binding.Parse> Ereignisse zu kombinieren und trennen Sie die `PhoneNumber` und `Extension` Felder aus der Grenze <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b55b3-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)   
        {  
            ext = "";  
        } else   
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.   
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.   
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8. <span data-ttu-id="b55b3-116">Hinzufügen von zwei <xref:System.Windows.Forms.Button> Steuerelemente im Formular.</span><span class="sxs-lookup"><span data-stu-id="b55b3-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="b55b3-117">Nennen Sie diese `previousButton` und `nextButton`.</span><span class="sxs-lookup"><span data-stu-id="b55b3-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="b55b3-118">Doppelklicken Sie auf jede Schaltfläche zum Hinzufügen einer <xref:System.Windows.Forms.Control.Click> -Ereignishandler, und geben Sie die Ereignishandler, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b55b3-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="b55b3-119">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="b55b3-119">Run the sample.</span></span> <span data-ttu-id="b55b3-120">Bearbeiten Sie die Daten, und Verwenden der **zurück** und **Weiter** Schaltflächen, um anzuzeigen, dass die Daten ordnungsgemäß, um beibehalten werden die <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b55b3-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b55b3-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b55b3-121">Example</span></span>  
 <span data-ttu-id="b55b3-122">Im folgenden Codebeispiel wird diese Ergebnisse aus der vorherigen Schritte für die vollständige codeauflistung.</span><span class="sxs-lookup"><span data-stu-id="b55b3-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](~/samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](~/samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b55b3-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b55b3-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="b55b3-124">Erstellen Sie eine Visualisierung C# oder Visual Basic-Projekt.</span><span class="sxs-lookup"><span data-stu-id="b55b3-124">Create a Visual C# or Visual Basic project.</span></span>  
  
-   <span data-ttu-id="b55b3-125">Hinzufügen der <xref:System.Windows.Forms.TextBox> und <xref:System.Windows.Forms.MaskedTextBox> Steuerelemente im Formular, wie im vorherigen Verfahren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b55b3-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
-   <span data-ttu-id="b55b3-126">Öffnen Sie die Quellcodedatei für das Formular des Projekts Standard.</span><span class="sxs-lookup"><span data-stu-id="b55b3-126">Open the source code file for the project's default form.</span></span>  
  
-   <span data-ttu-id="b55b3-127">Ersetzen Sie den Quellcode in dieser Datei durch den Code, der im vorherigen Abschnitt "Code" aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b55b3-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
-   <span data-ttu-id="b55b3-128">Kompilieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b55b3-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55b3-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b55b3-129">See also</span></span>

- [<span data-ttu-id="b55b3-130">Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b55b3-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
