---
title: Beibehalten eines Objekts in Visual Studio (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0ff6320aee65850b8b445f445f80b4bbe2c9c254
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a>Exemplarische Vorgehensweise: Beibehalten eines Objekts in Visual Studio (Visual Basic)
Obwohl Sie die Eigenschaften eines Objekts mit Standardwerten zur Entwurfszeit festlegen können, sind zur Laufzeit eingegebene Werte verloren, wenn das Objekt zerstört wird. Sie können die Serialisierung verwenden, zum Beibehalten der Daten eines Objekts zwischen Instanzen ermöglicht es Ihnen, Werte zu speichern und Abrufen der nächsten, der das Objekt instanziiert wird.  
  
> [!NOTE]
>  In Visual Basic zum Speichern einfacher Daten, wie Name oder Zahl, können Sie die `My.Settings` Objekt. Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie eine einfache `Loan` -Objekt und dessen Daten in einer Datei beibehalten. Die Daten werden dann aus der Datei abgerufen werden, wenn das Objekt neu erstellen.  
  
> [!IMPORTANT]
>  Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist. Wenn eine Anwendung eine Datei erstellen muss, muss die Anwendung `Create` Berechtigung für den Ordner. Berechtigungen werden mit Zugriffssteuerungslisten festgelegt. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich `Write` Berechtigung, eine geringere Berechtigung. Falls möglich, ist sicherer, erstellen die Datei während der Bereitstellung, und gewähren nur `Read` Berechtigungen für eine einzelne Datei (anstelle von Berechtigungen für einen Ordner erstellen). Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in den Stammordner oder den Ordner Programme zu schreiben.  
  
> [!IMPORTANT]
>  In diesem Beispiel speichert Daten in eine Binärdatei. Diese Formate sollten nicht für vertrauliche Daten wie Kennwörter oder Kreditkarteninformationen verwendet werden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-loan-object"></a>Erstellen des Loan-Objekts  
 Der erste Schritt ist die Erstellung einer `Loan` Klasse und einer Anwendung, die die Klasse verwendet.  
  
### <a name="to-create-the-loan-class"></a>So erstellen Sie die Loan-Klasse  
  
1.  Erstellen Sie ein neues Klassenbibliotheksprojekt, und nennen Sie es "LoanClass". Weitere Informationen finden Sie unter [Erstellen von Projekten und Projektmappen](http://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects).  
  
2.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die Datei Class1, und wählen Sie **umbenennen**. Benennen Sie die Datei `Loan` , und drücken Sie die EINGABETASTE. Umbenennen der Datei wird auch die Klasse umbenennen `Loan`.  
  
3.  Fügen Sie die folgenden öffentlichen Member der Klasse:  
  
    ```vb  
    Public Class Loan  
        Implements System.ComponentModel.INotifyPropertyChanged  
  
        Public Property LoanAmount As Double  
        Public Property InterestRate As Double  
        Public Property Term As Integer  
  
        Private p_Customer As String  
        Public Property Customer As String  
            Get  
                Return p_Customer  
            End Get  
            Set(ByVal value As String)  
                p_Customer = value  
                RaiseEvent PropertyChanged(Me,  
                  New System.ComponentModel.PropertyChangedEventArgs("Customer"))  
            End Set  
        End Property  
  
        Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
          Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
  
        Public Sub New(ByVal loanAmount As Double,  
                       ByVal interestRate As Double,  
                       ByVal term As Integer,  
                       ByVal customer As String)  
  
            Me.LoanAmount = loanAmount  
            Me.InterestRate = interestRate  
            Me.Term = term  
            p_Customer = customer  
        End Sub  
    End Class  
    ```  
  
 Sie müssen auch eine einfache Anwendung erstellen, verwendet die `Loan` Klasse.  
  
### <a name="to-create-a-test-application"></a>So erstellen Sie eine testanwendung  
  
1.  Um der Projektmappe ein Windows Forms-Anwendungsprojekt hinzuzufügen der **Datei** Menü wählen **hinzufügen**,**neues Projekt**.  
  
2.  In der **neues Projekt hinzufügen** Dialogfeld Wählen Sie **Windows Forms-Anwendung**, und geben Sie `LoanApp` als Namen für das Projekt, und klicken Sie dann auf **OK** um das Dialogfeld zu schließen.  
  
3.  In **Projektmappen-Explorer**, wählen Sie das LoanApp-Projekt.  
  
4.  Auf der **Projekt** Menü wählen **Set as StartUp Project**.  
  
5.  Wählen Sie im Menü **Projekt** den Eintrag **Verweis hinzufügen**aus.  
  
6.  In der **Verweis hinzufügen** Dialogfeld Wählen Sie die **Projekte** Registerkarte, und wählen Sie dann das Projekt LoanClass aus.  
  
7.  Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
8.  Fügen Sie im Designer vier <xref:System.Windows.Forms.TextBox>Steuerelemente im Formular.</xref:System.Windows.Forms.TextBox>  
  
9. Fügen Sie im Code-Editor folgenden Code hinzu:  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
10. Fügen Sie einen Ereignishandler für das `PropertyChanged` Ereignis, um das Formular mit dem folgenden Code:  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 An diesem Punkt können Sie erstellen und Ausführen der Anwendung. Beachten Sie, das die Standardwerte aus der `Loan` Klasse, die in den Textfeldern angezeigt. Ändern den Zinssatz-Wert von 7.5 7.1, und schließen Sie die Anwendung und führen Sie sie erneut versuchen, der auf den Standardwert von 7.5 wird zurückgesetzt.  
  
 In der realen Welt ändern, Zinssätze in regelmäßigen Abständen, aber nicht unbedingt bei jedem Ausführen der Anwendung. Anstatt den Benutzer, der den Zinssatz jedes Mal aktualisieren, die die Anwendung ausgeführt wird, ist es besser, den aktuellen Zinssatz zwischen Instanzen der Anwendung beibehalten. Im nächsten Schritt werden Sie nur dazu Serialisierung die Loan-Klasse hinzufügen.  
  
## <a name="using-serialization-to-persist-the-object"></a>Mithilfe der Serialisierung des Objekts  
 Um die Werte für die Loan-Klasse erhalten bleiben, müssen Sie zunächst die Klasse mit markieren die `Serializable` Attribut.  
  
### <a name="to-mark-a-class-as-serializable"></a>Eine Klasse als serialisierbar markiert  
  
-   Ändern Sie die Klassendeklaration für die Loan-Klasse wie folgt:  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 Das `Serializable` -Attribut weist den Compiler, dass alles in der Klasse in einer Datei beibehalten werden kann. Da die `PropertyChanged` -Ereignis von einem Windows Form-Objekt behandelt werden, können nicht serialisiert werden. Die `NonSerialized` Attribut kann verwendet werden, um Klassenmember zu markieren, die nicht beibehalten werden sollen.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>Um zu verhindern, dass einen Member serialisiert werden  
  
-   Ändern Sie die Deklaration für die `PropertyChanged` Ereignis wie folgt:  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 Im nächste Schritt wird der LoanApp-Anwendung den Serialisierungscode hinzu. Um die Klasse zu serialisieren und in eine Datei zu schreiben, verwenden Sie die <xref:System.IO>und <xref:System.Xml.Serialization>Namespaces.</xref:System.Xml.Serialization> </xref:System.IO> Um zu vermeiden, die vollqualifizierten Namen eingeben, können Sie Verweise auf die erforderlichen Klassenbibliotheken hinzufügen.  
  
### <a name="to-add-references-to-namespaces"></a>Hinzufügen von Verweisen auf namespaces  
  
-   Fügen Sie die folgenden Anweisungen am Anfang der `Form1` Klasse:  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     In diesem Fall verwenden Sie ein binäres Formatierungsprogramm, um das Objekt in einem binären Format zu speichern.  
  
 Der nächste Schritt ist, Code hinzufügen, um das Objekt aus der Datei deserialisiert, wenn das Objekt erstellt wird.  
  
### <a name="to-deserialize-an-object"></a>So deserialisieren Sie ein Objekt  
  
1.  Fügen Sie eine Konstante zur Klasse für den Dateinamen der serialisierten Daten.  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2.  Ändern Sie den Code in der `Form1_Load` -Ereignisprozedur wie folgt:  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        If File.Exists(FileName) Then  
            Dim TestFileStream As Stream = File.OpenRead(FileName)  
            Dim deserializer As New BinaryFormatter  
            TestLoan = CType(deserializer.Deserialize(TestFileStream), LoanClass.Loan)  
            TestFileStream.Close()  
        End If  
  
        AddHandler TestLoan.PropertyChanged, AddressOf Me.CustomerPropertyChanged  
  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
     Beachten Sie, dass zuerst Sie sich vergewissern müssen, dass die Datei vorhanden ist. Wenn vorhanden, erstellen Sie eine <xref:System.IO.Stream>Klasse zum Lesen der Binärdatei und eine <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>Klasse zum Übersetzen der Datei.</xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> </xref:System.IO.Stream> Sie müssen auch in den Loan-Objekttyp aus dem Streamtyp zu konvertieren.  
  
 Als Nächstes müssen Sie Code zum Speichern der Daten in die Textfelder eingegebenen Hinzufügen der `Loan` -Klasse, und dann die Klasse in einer Datei serialisieren.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>Speichern Sie die Daten und die Klasse serialisieren  
  
-   Fügen Sie den folgenden Code der `Form1_FormClosing` Ereignisprozedur:  
  
    ```vb  
    Private Sub Form1_FormClosing() Handles MyBase.FormClosing  
        TestLoan.LoanAmount = CDbl(TextBox1.Text)  
        TestLoan.InterestRate = CDbl(TextBox2.Text)  
        TestLoan.Term = CInt(TextBox3.Text)  
        TestLoan.Customer = TextBox4.Text  
  
        Dim TestFileStream As Stream = File.Create(FileName)  
        Dim serializer As New BinaryFormatter  
        serializer.Serialize(TestFileStream, TestLoan)  
        TestFileStream.Close()  
    End Sub  
    ```  
  
 An diesem Punkt können Sie erneut erstellen und Ausführen der Anwendung. Zunächst werden die Standardwerte in den Textfeldern angezeigt. Versuchen Sie, die Werte ändern, und geben im vierten Textfeld. Schließen Sie die Anwendung, und führen Sie sie erneut aus. Beachten Sie, dass die neuen Werte jetzt in den Textfeldern angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)   
 [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
