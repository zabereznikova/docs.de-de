---
title: 'Exemplarische Vorgehensweise: Beibehalten eines Objekts in Visual Studio (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: get-started-article
ms.assetid: a544ce46-ee25-49da-afd4-457a3d59bf63
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b1a3fc377875ee25baa0718a25b5ac509822154
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-c"></a>Exemplarische Vorgehensweise: Beibehalten eines Objekts in Visual Studio (C#)
Obwohl Sie die Eigenschaften eines Objekts während der Entwurfszeit auf Standardwerte festlegen können, gehen während der Laufzeit eingegebene Werte verloren, wenn das Objekt zerstört wird. Sie können die Serialisierung verwenden, um die Daten eines Objekts zwischen Instanzen beizubehalten. Dadurch können Sie Werte speichern und abrufen, wenn das Objekt das nächste Mal instanziiert wird.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches `Loan`-Objekt und behalten dessen Daten in einer Datei bei. Anschließend rufen Sie die Daten aus der Datei ab, wenn Sie das Objekt neu erstellen.  
  
> [!IMPORTANT]
>  Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist. Wenn eine Anwendung eine Datei erstellen muss, muss Sie über die `Create`-Berechtigung für den Ordner verfügen. Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung `Write`, was einer geringeren Berechtigung entspricht. Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte die `Read`-Berechtigung nur für eine einzelne Datei erteilt werden (anstatt „Create“-Berechtigungen für den gesamten Ordner zu gewähren). Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programme“ zu schreiben.  
  
> [!IMPORTANT]
>  In diesem Beispiel werden Daten in einer Datei im Binärformat gespeichert. Diese Formate sollten nicht für sensible Daten wie Kennwörter oder Kreditkarteninformationen verwendet werden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-loan-object"></a>Erstellen des Loan-Objekts  
 Der erste Schritt ist das Erstellen einer `Loan`-Klasse und einer Testanwendung, die die Klasse verwendet.  
  
### <a name="to-create-the-loan-class"></a>So erstellen Sie eine Loan-Klasse  
  
1.  Erstellen Sie ein neues Klassenbibliotheksprojekt mit dem Namen „LoanClass“. Weitere Informationen finden Sie unter [Erstellen von Projekten und Projektmappen](/visualstudio/ide/creating-solutions-and-projects).  
  
2.  Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für die Datei „Class1“ und wählen Sie **Umbenennen** aus. Benennen Sie die Datei in `Loan` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `Loan` umbenannt.  
  
3.  Fügen Sie der Klasse die folgenden öffentlichen Member hinzu:  
  
    ```csharp  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
        public double LoanAmount {get; set;}  
        public double InterestRate {get; set;}  
        public int Term {get; set;}  
  
        private string p_Customer;  
        public string Customer  
        {  
            get { return p_Customer; }  
            set   
            {  
                p_Customer = value;  
                PropertyChanged(this,  
                  new System.ComponentModel.PropertyChangedEventArgs("Customer"));  
            }  
        }  
  
        public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
  
        public Loan(double loanAmount,  
                    double interestRate,  
                    int term,  
                    string customer)  
        {  
            this.LoanAmount = loanAmount;  
            this.InterestRate = interestRate;  
            this.Term = term;  
            p_Customer = customer;  
        }  
    }  
    ```  
  
 Sie müssen ebenfalls eine einfache Anwendung erstellen, die die `Loan`-Klasse verwendet.  
  
### <a name="to-create-a-test-application"></a>So erstellen Sie eine Testanwendung  
  
1.  Wählen Sie im Menü **Datei** **Hinzufügen** und **Neues Projekt** aus, um ein Windows Forms-Anwendungsprojekt zu Ihrer Projektmappe hinzuzufügen.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** **Windows Forms-Anwendung** aus, und geben Sie als Namen für das Projekt `LoanApp` ein. Klicken Sie anschließend auf **OK**, um das Dialogfeld zu schließen.  
  
3.  Wählen Sie im **Projektmappen-Explorer** das LoanApp-Projekt aus.  
  
4.  Klicken Sie im Menü **Projekt** auf **Als Startprojekt festlegen**.  
  
5.  Wählen Sie im Menü **Projekt** den Eintrag **Verweis hinzufügen**aus.  
  
6.  Wählen Sie im Dialogfeld **Verweis hinzufügen** die Registerkarte **Projekte** und anschließend das LoanClass-Projekt aus.  
  
7.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
8.  Fügen Sie dem Formular im Designer vier <xref:System.Windows.Forms.TextBox>-Steuerelemente hinzu.  
  
9. Fügen Sie im Code-Editor folgenden Code hinzu:  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
10. Fügen Sie dem Formular mithilfe des folgenden Codes einen Ereignishandler für das Ereignis `PropertyChanged` hinzu:  
  
    ```csharp  
    private void CustomerPropertyChanged(object sender,   
        System.ComponentModel.PropertyChangedEventArgs e)  
    {  
        MessageBox.Show(e.PropertyName + " has been changed.");  
    }  
    ```  
  
 Nun können Sie die Anwendung erstellen und ausführen. Beachten Sie, dass die Standardwerte aus der `Loan`-Klasse in den Textfeldern angezeigt werden. Versuchen Sie, den Wert „Zinssatz“ von 7,5 zu 7,1 zu ändern, schließen Sie die Anwendung, und führen Sie sie erneut aus – der Wert wird auf den Standardwert 7,5 zurückgesetzt.  
  
 In der Praxis ändern sich Zinssätze regelmäßig, aber nicht unbedingt jedes Mal wenn die Anwendung ausgeführt wird. Es ist besser, den aktuellsten Zinssatz zwischen zwei Instanzen der Anwendung beizubehalten, anstatt den Benutzer den Zinssatz bei jeder Ausführung der Anwendung aktualisieren zu lassen. Im nächsten Schritt werden Sie durch Hinzufügen von Serialisierung zur Loan-Klasse genau das tun.  
  
## <a name="using-serialization-to-persist-the-object"></a>Verwenden von Serialisierung zum Beibehalten des Objekts  
 Sie müssen die Klasse zuerst mit dem Attribut `Serializable` markieren, um die Werte für die Loan-Klasse beizubehalten.  
  
### <a name="to-mark-a-class-as-serializable"></a>So markieren Sie eine Klasse als serialisierbar  
  
-   Ändern Sie die Klassendeklaration für die Loan-Klasse wie folgt:  
  
    ```csharp  
    [Serializable()]  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
    ```  
  
 Der Compiler wird vom Attribut `Serializable` darüber informiert, dass der Inhalt der Klasse in einer Datei beibehalten werden kann. Da das Ereignis `PropertyChanged` von einem Windows Form-Objekt behandelt wird, kann es nicht serialisiert werden. Das Attribut `NonSerialized` kann dazu verwendet werden, Klassenmember zu markieren, die nicht beibehalten werden sollen.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>So verhindern Sie, dass ein Member serialisiert wird  
  
-   Ändern Sie die Deklaration für das Ereignis `PropertyChanged` wie folgt:  
  
    ```csharp  
    [field: NonSerialized()]  
    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
    ```  
  
 Fügen Sie als nächstes den Serialisierungscode zur LoanApp-Anwendung hinzu. Um die Klasse zu serialisieren und in eine Datei zu schreiben, verwenden Sie die Namespaces <xref:System.IO> und <xref:System.Xml.Serialization>. Sie können Verweise zu den notwendigen Klassenbibliotheken hinzufügen, damit Sie die vollqualifizierten Namen nicht eingeben müssen.  
  
### <a name="to-add-references-to-namespaces"></a>So fügen Sie Verweise zu Namespaces hinzu  
  
-   Fügen Sie am Anfang der `Form1`-Klasse die folgenden Anweisungen ein:  
  
    ```csharp  
    using System.IO;  
    using System.Runtime.Serialization.Formatters.Binary;  
    ```  
  
     In diesem Fall verwenden Sie ein binäres Formatierungsprogramm, um ein Objekt im Binärformat zu speichern.  
  
 Fügen Sie als nächstes Code hinzu, um das Objekt aus der Datei zu deserialisieren wenn das Objekt erstellt wird.  
  
### <a name="to-deserialize-an-object"></a>So deserialisieren Sie ein Objekt  
  
1.  Fügen Sie eine Konstante zur Klasse für den Dateinamen der serialisierten Daten hinzu.  
  
    ```csharp  
    const string FileName = @"..\..\SavedLoan.bin";  
    ```  
  
2.  Ändern Sie den Code der `Form1_Load`-Ereignisprozedur wie folgt:  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        if (File.Exists(FileName))  
        {  
            Stream TestFileStream = File.OpenRead(FileName);  
            BinaryFormatter deserializer = new BinaryFormatter();  
            TestLoan = (LoanClass.Loan)deserializer.Deserialize(TestFileStream);  
            TestFileStream.Close();  
        }  
  
        TestLoan.PropertyChanged += this.CustomerPropertyChanged;  
  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
     Beachten Sie, dass Sie erst sicherstellen müssen, ob die Datei vorhanden ist. Wenn sie vorhanden ist, erstellen Sie eine <xref:System.IO.Stream>-Klasse zum Lesen der Binärdatei und eine <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Klasse zum Übersetzen der Datei. Sie müssen ebenfalls vom Streamtyp in den Loan-Objekttyp konvertieren.  
  
 Als nächstes müssen Sie Code hinzufügen, um die in die Textfelder eingegebenen Daten in der `Loan`-Klasse zu speichern. Anschließend müssen Sie die Klasse in eine Datei serialisieren.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>So speichern Sie die Daten und serialisieren die Klasse  
  
-   Fügen Sie den folgenden Code zur `Form1_FormClosing`-Ereignisprozedur hinzu:  
  
    ```csharp  
    private void Form1_FormClosing(object sender, FormClosingEventArgs e)  
    {  
        TestLoan.LoanAmount = Convert.ToDouble(textBox1.Text);  
        TestLoan.InterestRate = Convert.ToDouble(textBox2.Text);  
        TestLoan.Term = Convert.ToInt32(textBox3.Text);  
        TestLoan.Customer = textBox4.Text;  
  
        Stream TestFileStream = File.Create(FileName);  
        BinaryFormatter serializer = new BinaryFormatter();  
        serializer.Serialize(TestFileStream, TestLoan);  
        TestFileStream.Close();  
    }  
    ```  
  
 Nun können Sie die Anwendung erneut erstellen und ausführen. Zuerst werden die Standardwerte in den Textfeldern angezeigt. Versuchen Sie, die Werte zu ändern, und geben Sie einen Namen in das vierte Textfeld ein. Schließen Sie die Anwendung, und führen Sie sie dann erneut aus. Beachten Sie, dass die neuen Werte jetzt in den Textfeldern erscheinen.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md)  
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)
