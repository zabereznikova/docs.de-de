---
title: Verwenden von Rückrufen in Windows-Anwendungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ae2ea457-0764-4b06-8977-713c77e85bd2
ms.openlocfilehash: 9f1e3fe6d53266a4e1366c1a3d5396688a25df0f
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44708597"
---
# <a name="windows-applications-using-callbacks"></a><span data-ttu-id="8588d-102">Verwenden von Rückrufen in Windows-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8588d-102">Windows Applications Using Callbacks</span></span>
<span data-ttu-id="8588d-103">In den meisten asynchronen Verarbeitungsszenarien möchten Sie eine Datenbankoperation starten und weitere Prozesse ausführen, ohne dabei warten zu müssen, bis die Datenbankoperation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8588d-103">In most asynchronous processing scenarios, you want to start a database operation and continue running other processes without waiting for the database operation to complete.</span></span> <span data-ttu-id="8588d-104">Viele Szenarien erfordern allerdings nach dem Beenden der Datenbankoperation eine Aktion.</span><span class="sxs-lookup"><span data-stu-id="8588d-104">However, many scenarios require doing something once the database operation has ended.</span></span> <span data-ttu-id="8588d-105">So möchten Sie beispielsweise in einer Windows-Anwendung die länger dauernde Operation an einen Hintergrundthread weitergeben, während der Benutzeroberflächenthread weiterhin reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="8588d-105">In a Windows application, for example, you may want to delegate the long-running operation to a background thread while allowing the user interface thread to remain responsive.</span></span> <span data-ttu-id="8588d-106">Nach dem Beenden der Datenbankoperation möchten Sie allerdings die Ergebnisse verwenden, um das Formular zu füllen.</span><span class="sxs-lookup"><span data-stu-id="8588d-106">However, when the database operation is complete, you want to use the results to populate the form.</span></span> <span data-ttu-id="8588d-107">Dieser Typ von Szenario wird am Besten durch einen Rückruf implementiert.</span><span class="sxs-lookup"><span data-stu-id="8588d-107">This type of scenario is best implemented with a callback.</span></span>  
  
 <span data-ttu-id="8588d-108">Einen Rückruf implementieren Sie, indem Sie einen <xref:System.AsyncCallback>-Delegaten in der <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>-Methode, der <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A>-Methode oder der <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A>-Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="8588d-108">You define a callback by specifying an <xref:System.AsyncCallback> delegate in the <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A>, or <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> method.</span></span> <span data-ttu-id="8588d-109">Der Delegat wird nach Abschluss der Operation aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8588d-109">The delegate is called when the operation is complete.</span></span> <span data-ttu-id="8588d-110">Sie können dem Delegaten einen Verweis auf den <xref:System.Data.SqlClient.SqlCommand> selbst zuweisen, wodurch der Zugriff auf das <xref:System.Data.SqlClient.SqlCommand>-Objekt und das Aufrufen der passenden `End`-Methode vereinfacht wird, ohne eine globale Variable verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="8588d-110">You can pass the delegate a reference to the <xref:System.Data.SqlClient.SqlCommand> itself, making it easy to access the <xref:System.Data.SqlClient.SqlCommand> object and call the appropriate `End` method without having to use a global variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8588d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8588d-111">Example</span></span>  
 <span data-ttu-id="8588d-112">In der folgenden Windows-Anwendung wird die Verwendung der <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>-Methode gezeigt, wobei eine Transact-SQL-Anweisung ausgeführt wird, die eine Verzögerung von einigen Sekunden beinhaltet (Emulieren eines zeitintensiven Befehls).</span><span class="sxs-lookup"><span data-stu-id="8588d-112">The following Windows application demonstrates the use of the <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A> method, executing a Transact-SQL statement that includes a delay of a few seconds (emulating a long-running command).</span></span>  
  
 <span data-ttu-id="8588d-113">In diesem Beispiel werden einige wichtige Techniken gezeigt, darunter das Aufrufen einer Methode, die mit dem Formular von einem separaten Thread aus zusammenwirkt.</span><span class="sxs-lookup"><span data-stu-id="8588d-113">This example demonstrates a number of important techniques, including calling a method that interacts with the form from a separate thread.</span></span> <span data-ttu-id="8588d-114">Zusätzlich zeigt dieses Beispiel, wie Sie Benutzer vom mehrfachen Ausführen eines Befehls abhalten können und wie Sie sicherstellen müssen, dass das Formular nicht vor dem Aufruf der Rückrufprozedur geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="8588d-114">In addition, this example demonstrates how you must block users from concurrently executing a command multiple times, and how you must ensure that the form does not close before the callback procedure is called.</span></span>  
  
 <span data-ttu-id="8588d-115">Erstellen Sie zum Einrichten dieses Beispiels eine neue Windows-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8588d-115">To set up this example, create a new Windows application.</span></span> <span data-ttu-id="8588d-116">Positionieren Sie ein <xref:System.Windows.Forms.Button>-Steuerelement und zwei <xref:System.Windows.Forms.Label>-Steuerelemente auf dem Formular (übernehmen Sie für jedes Steuerelement den Standardnamen).</span><span class="sxs-lookup"><span data-stu-id="8588d-116">Place a <xref:System.Windows.Forms.Button> control and two <xref:System.Windows.Forms.Label> controls on the form (accepting the default name for each control).</span></span> <span data-ttu-id="8588d-117">Fügen Sie der Klasse des Formulars folgenden Code hinzu. Ändern Sie die Verbindungszeichenfolge entsprechend der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="8588d-117">Add the following code to the form's class, modifying the connection string as necessary for your environment.</span></span>  
  
```vb  
' Add these to the top of the class:  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
  
' Add this code to the form's class:  
  
    ' You'll need this delegate in order to display text from a   
    ' thread other than the form's thread. See the HandleCallback  
    ' procedure for more information.  
    ' This same delegate matches both the DisplayStatus   
    ' and DisplayResults methods.  
    Private Delegate Sub DisplayInfoDelegate(ByVal Text As String)  
  
    ' This flag ensures that the user doesn't attempt  
    ' to restart the command or close the form while the   
    ' asynchronous command is executing.  
    Private isExecuting As Boolean  
  
    ' This example maintains the connection object   
    ' externally, so that it's available for closing.  
    Private connection As SqlConnection  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,              
        ' you can retrieve it from a configuration file.   
  
        ' If you have not included "Asynchronous Processing=true"  
        ' in the connection string, the command will not be able  
        ' to execute asynchronously.  
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks;" & _  
          "Asynchronous Processing=true"  
    End Function  
  
    Private Sub DisplayStatus(ByVal Text As String)  
        Me.Label1.Text = Text  
    End Sub  
  
    Private Sub DisplayResults(ByVal Text As String)  
        Me.Label1.Text = Text  
        DisplayStatus("Ready")  
    End Sub  
  
    Private Sub Form1_FormClosing(ByVal sender As Object, _  
        ByVal e As System.Windows.Forms.FormClosingEventArgs) _  
        Handles Me.FormClosing  
        If isExecuting Then  
            MessageBox.Show(Me, "Can't close the form until " & _  
             "the pending asynchronous command has completed. " & _  
             "Please wait...")  
            e.Cancel = True  
        End If  
    End Sub  
  
    Private Sub Button1_Click( _  
        ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles Button1.Click  
        If isExecuting Then  
            MessageBox.Show(Me, _  
                "Already executing. " & _  
                "Please wait until the current query " & _  
                "has completed.")  
        Else  
            Dim command As SqlCommand  
            Try  
                DisplayResults("")  
                DisplayStatus("Connecting...")  
                connection = New SqlConnection(GetConnectionString())  
                ' To emulate a long-running query, wait for   
                ' a few seconds before working with the data.  
                ' This command doesn't do much, but that's the point--  
                ' it doesn't change your data, in the long run.  
                Dim commandText As String = _  
                    "WAITFOR DELAY '0:0:05';" & _  
                    "UPDATE Production.Product " & _  
                    "SET ReorderPoint = ReorderPoint + 1 " & _  
                    "WHERE ReorderPoint Is Not Null;" & _  
                    "UPDATE Production.Product " & _  
                    "SET ReorderPoint = ReorderPoint - 1 " & _  
                    "WHERE ReorderPoint Is Not Null"  
  
                command = New SqlCommand(commandText, connection)  
                connection.Open()  
  
                DisplayStatus("Executing...")  
                isExecuting = True  
                ' Although it's not required that you pass the   
                ' SqlCommand object as the second parameter in the   
                ' BeginExecuteNonQuery call, doing so makes it easier  
                ' to call EndExecuteNonQuery in the callback procedure.  
                Dim callback As New _  
                      AsyncCallback(AddressOf HandleCallback)  
  
                ' Once the BeginExecuteNonQuery method is called,  
                ' the code continues--and the user can interact with  
                ' the form--while the server executes the query.  
  
                command.BeginExecuteNonQuery(callback, command)  
  
            Catch ex As Exception  
                isExecuting = False  
                DisplayStatus( _  
                    String.Format("Ready (last error: {0})", _  
                    ex.Message))  
                If connection IsNot Nothing Then  
                    connection.Close()  
                End If  
            End Try  
        End If  
    End Sub  
  
    Private Sub HandleCallback(ByVal result As IAsyncResult)  
        Try  
            ' Retrieve the original command object, passed  
            ' to this procedure in the AsyncState property  
            ' of the IAsyncResult parameter.  
            Dim command As SqlCommand = _  
                CType(result.AsyncState, SqlCommand)  
            Dim rowCount As Integer = _  
                command.EndExecuteNonQuery(result)  
            Dim rowText As String = " rows affected."  
            If rowCount = 1 Then  
                rowText = " row affected."  
            End If  
            rowText = rowCount & rowText  
  
            ' You may not interact with the form and its contents  
            ' from a different thread, and this callback procedure  
            ' is all but guaranteed to be running from a different   
            ' thread than the form. Therefore you cannot simply call   
            ' code that displays the results, like this:  
            ' DisplayResults(rowText)  
  
            ' Instead, you must call the procedure from the form's  
            ' thread. One simple way to accomplish this is to call   
            ' the Invoke method of the form, which calls the delegate   
            ' you supply from the form's thread.   
            Dim del As New _  
                DisplayInfoDelegate(AddressOf DisplayResults)  
            Me.Invoke(del, rowText)  
  
        Catch ex As Exception  
            ' Because you're now running code in a separate thread,   
            ' if you don't handle the exception here, none of your   
            ' other code will catch the exception. Because none of   
            ' your code is on the call stack in this thread, there's   
            ' nothing higher up the stack to catch the exception if   
            ' you don't handle it here. You can either log the   
            ' exception or invoke a delegate (as in the non-error   
            ' case in this example) to display the error on the form.   
            ' In no case can you simply display the error without   
            ' executing a delegate as in the Try block here.  
  
            ' You can create the delegate instance as you   
            ' invoke it, like this:  
            Me.Invoke(New _  
                DisplayInfoDelegate(AddressOf DisplayStatus), _  
                String.Format("Ready(last error: {0}", ex.Message))  
        Finally  
            isExecuting = False  
            If connection IsNot Nothing Then  
                connection.Close()  
            End If  
        End Try  
    End Sub  
```  
  
```csharp  
// Add these to the top of the class, if they're not already there:  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
// Hook up the form's Load event handler (you can double-click on   
// the form's design surface in Visual Studio), and then add   
// this code to the form's class:  
  
// You'll need this delegate in order to display text from a thread  
// other than the form's thread. See the HandleCallback  
// procedure for more information.  
// This same delegate matches both the DisplayStatus   
// and DisplayResults methods.  
private delegate void DisplayInfoDelegate(string Text);  
  
// This flag ensures that the user doesn't attempt  
// to restart the command or close the form while the   
// asynchronous command is executing.  
private bool isExecuting;  
  
// This example maintains the connection object   
// externally, so that it's available for closing.  
private SqlConnection connection;  
  
private static string GetConnectionString()  
{  
    // To avoid storing the connection string in your code,              
    // you can retrieve it from a configuration file.   
  
    // If you have not included "Asynchronous Processing=true" in the  
    // connection string, the command will not be able  
    // to execute asynchronously.  
    return "Data Source=(local);Integrated Security=SSPI;" +  
    "Initial Catalog=AdventureWorks; Asynchronous Processing=true";  
}  
  
private void DisplayStatus(string Text)  
{  
    this.label1.Text = Text;  
}  
  
private void DisplayResults(string Text)  
{  
    this.label1.Text = Text;  
    DisplayStatus("Ready");  
}  
  
private void Form1_FormClosing(object sender, System.Windows.Forms.FormClosingEventArgs e)  
{  
    if (isExecuting)  
    {  
        MessageBox.Show(this, "Can't close the form until " +  
        "the pending asynchronous command has completed. Please " +  
        wait...");  
        e.Cancel = true;  
    }  
}  
  
private void button1_Click(object sender, System.EventArgs e)  
{  
    if (isExecuting)  
    {  
        MessageBox.Show(this, "Already executing. Please wait until " +  
        "the current query has completed.");  
    }  
    else  
    {  
        SqlCommand command = null;  
        try  
        {  
            DisplayResults("");  
            DisplayStatus("Connecting...");  
            connection = new SqlConnection(GetConnectionString());  
            // To emulate a long-running query, wait for   
            // a few seconds before working with the data.  
            // This command doesn't do much, but that's the point--  
            // it doesn't change your data, in the long run.  
            string commandText =  
                "WAITFOR DELAY '0:0:05';" +  
                "UPDATE Production.Product " +  
                "SET ReorderPoint = ReorderPoint + 1 " +  
                "WHERE ReorderPoint Is Not Null;" +  
                "UPDATE Production.Product " +  
                "SET ReorderPoint = ReorderPoint - 1 " +  
                "WHERE ReorderPoint Is Not Null";  
  
            command = new SqlCommand(commandText, connection);  
            connection.Open();  
  
            DisplayStatus("Executing...");  
            isExecuting = true;  
            // Although it's not required that you pass the   
            // SqlCommand object as the second parameter in the   
            // BeginExecuteNonQuery call, doing so makes it easier  
            // to call EndExecuteNonQuery in the callback procedure.  
            AsyncCallback callback = new AsyncCallback(HandleCallback);  
  
            // Once the BeginExecuteNonQuery method is called,  
            // the code continues--and the user can interact with  
            // the form--while the server executes the query.  
            command.BeginExecuteNonQuery(callback, command);  
  
        }  
        catch (Exception ex)  
        {  
            isExecuting = false;  
            DisplayStatus(   
             string.Format("Ready (last error: {0})", ex.Message));  
            if (connection != null)  
            {  
                connection.Close();  
            }  
        }  
    }  
}  
  
private void HandleCallback(IAsyncResult result)  
{  
    try  
    {  
        // Retrieve the original command object, passed  
        // to this procedure in the AsyncState property  
        // of the IAsyncResult parameter.  
        SqlCommand command = (SqlCommand)result.AsyncState;  
        int rowCount = command.EndExecuteNonQuery(result);  
        string rowText = " rows affected.";  
        if (rowCount == 1)  
        {  
            rowText = " row affected.";  
        }  
        rowText = rowCount + rowText;  
  
        // You may not interact with the form and its contents  
        // from a different thread, and this callback procedure  
        // is all but guaranteed to be running from a different thread  
        // than the form. Therefore you cannot simply call code that   
        // displays the results, like this:  
        // DisplayResults(rowText)  
  
        // Instead, you must call the procedure from the form's thread.  
        // One simple way to accomplish this is to call the Invoke  
        // method of the form, which calls the delegate you supply  
        // from the form's thread.   
        DisplayInfoDelegate del =   
         new DisplayInfoDelegate(DisplayResults);  
        this.Invoke(del, rowText);  
    }  
    catch (Exception ex)  
    {  
        // Because you're now running code in a separate thread,   
        // if you don't handle the exception here, none of your other  
        // code will catch the exception. Because none of your  
        // code is on the call stack in this thread, there's nothing  
        // higher up the stack to catch the exception if you don't   
        // handle it here. You can either log the exception or   
        // invoke a delegate (as in the non-error case in this   
        // example) to display the error on the form. In no case  
        // can you simply display the error without executing a   
        // delegate as in the try block here.   
  
        // You can create the delegate instance as you   
        // invoke it, like this:  
        this.Invoke(new DisplayInfoDelegate(DisplayStatus),  
        String.Format("Ready(last error: {0}", ex.Message));  
    }  
    finally  
    {  
        isExecuting = false;  
        if (connection != null)  
        {  
            connection.Close();  
        }  
    }  
}  
  
private void Form1_Load(object sender, System.EventArgs e)  
{  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    this.FormClosing += new System.Windows.Forms.  
        FormClosingEventHandler(this.Form1_FormClosing);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8588d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8588d-118">See Also</span></span>  
 [<span data-ttu-id="8588d-119">Asynchrone Vorgänge</span><span class="sxs-lookup"><span data-stu-id="8588d-119">Asynchronous Operations</span></span>](../../../../../docs/framework/data/adonet/sql/asynchronous-operations.md)  
 [<span data-ttu-id="8588d-120">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="8588d-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
