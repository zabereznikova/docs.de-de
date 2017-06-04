---
title: "Gewusst wie: Binden von Daten an das MaskedTextBox-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datenbindung, MaskedTextBox-Steuerelement [Windows Forms]"
  - "MaskedTextBox-Steuerelement [Windows Forms]"
  - "MaskedTextBox-Steuerelement [Windows Forms], Binden von Daten"
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Binden von Daten an das MaskedTextBox-Steuerelement
Daten lassen sich an ein <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement wie an jedes andere Windows Forms\-Steuerelement binden.  Wenn das Format der in der Datenbank enthaltenen Daten jedoch nicht mit dem von der Maskendefinition erwarteten Format übereinstimmt, müssen die Daten neu formatiert werden.  Im folgenden Verfahren wird dies veranschaulicht. Dabei verwenden Sie das <xref:System.Windows.Forms.Binding.Format>\-Ereignis und das <xref:System.Windows.Forms.Binding.Parse>\-Ereignis der <xref:System.Windows.Forms.Binding>\-Klasse, um zwei separate Datenbankfelder für Telefonnummer und Durchwahl als einzelnes bearbeitbares Feld anzuzeigen.  
  
 Für das folgende Verfahren benötigen Sie Zugriff auf eine SQL Server\-Datenbank mit installierter Beispieldatenbank Northwind.  
  
### So binden Sie Daten an ein MaskedTextBox\-Steuerelement  
  
1.  Erstellen Sie ein neues Projekt vom Typ Windows Forms.  
  
2.  Ziehen Sie zwei <xref:System.Windows.Forms.TextBox>\-Steuerelemente auf das Formular, und nennen Sie diese `FirstName` und `LastName`.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement auf das Formular, und nennen Sie dieses `PhoneMask`.  
  
4.  Legen Sie die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>\-Eigenschaft von `PhoneMask` auf `(000) 000-0000 x9999` fest.  
  
5.  Fügen Sie dem Formular folgende Namespaceimporte hinzu.  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6.  Klicken Sie mit der rechten Maustaste auf das Formular, und wählen Sie **Code anzeigen**.  Fügen Sie diesen Code an einer beliebigen Stelle in der Formularklasse ein.  
  
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
  
7.  Fügen Sie Ereignishandler für das <xref:System.Windows.Forms.Binding.Format>\-Ereignis und das <xref:System.Windows.Forms.Binding.Parse>\-Ereignis hinzu, um die Felder `PhoneNumber` und `Extension` zu kombinieren und vom gebundenen <xref:System.Data.DataSet> zu trennen.  
  
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
  
8.  Fügen Sie dem Formular zwei <xref:System.Windows.Forms.Button>\-Steuerelemente hinzu.  Nennen Sie diese `previousButton` und `nextButton`.  Doppelklicken Sie auf jede Schaltfläche, um einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler hinzuzufügen, und füllen Sie die Ereignishandler, wie im folgenden Codebeispiel veranschaulicht, mit Daten.  
  
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
  
9. Führen Sie das Beispiel aus.  Bearbeiten Sie die Daten, und verwenden Sie die Schaltflächen **Zurück** und **Weiter**, um zu überprüfen, ob die Daten einwandfrei in <xref:System.Data.DataSet> übernommen wurden.  
  
## Beispiel  
 Beim folgenden Codebeispiel handelt es sich um die vollständige Codeauflistung, die sich aus der Ausführung des vorherigen Verfahrens ergibt.  
  
 [!code-cpp[MaskedTextBoxData#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\-Projekt oder ein [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\-Projekt.  
  
-   Fügen Sie dem Formular das <xref:System.Windows.Forms.TextBox>\-Steuerelement und das <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement hinzu, wie im vorherigen Verfahren beschrieben.  
  
-   Öffnen Sie die Quellcodedatei für das Standardformular des Projekts.  
  
-   Ersetzen Sie den Quellcode in dieser Datei durch den im vorherigen "Code"\-Abschnitt aufgelisteten Code.  
  
-   Kompilieren Sie die Anwendung.  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)