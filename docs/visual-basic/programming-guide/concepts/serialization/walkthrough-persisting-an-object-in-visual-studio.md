---
title: Beibehalten eines Objekts in Visual Studio
ms.date: 07/20/2015
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
ms.openlocfilehash: 3febd3f74510d11a7103edbd52bcae8043a5edc0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558601"
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a><span data-ttu-id="3a427-102">Exemplarische Vorgehensweise: Beibehalten eines Objekts in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a427-102">Walkthrough: Persisting an Object in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="3a427-103">Obwohl Sie die Eigenschaften eines Objekts während der Entwurfszeit auf Standardwerte festlegen können, gehen während der Laufzeit eingegebene Werte verloren, wenn das Objekt zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="3a427-103">Although you can set an object's properties to default values at design time, any values entered at run time are lost when the object is destroyed.</span></span> <span data-ttu-id="3a427-104">Sie können die Serialisierung verwenden, um die Daten eines Objekts zwischen Instanzen beizubehalten. Dadurch können Sie Werte speichern und abrufen, wenn das Objekt das nächste Mal instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="3a427-104">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a427-105">Um einfache Daten wie einen Namen oder eine Zahl zu speichern, können Sie in Visual Basic das `My.Settings`-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a427-105">In Visual Basic, to store simple data, such as a name or number, you can use the `My.Settings` object.</span></span> <span data-ttu-id="3a427-106">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="3a427-106">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
 <span data-ttu-id="3a427-107">In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches `Loan`-Objekt und behalten dessen Daten in einer Datei bei.</span><span class="sxs-lookup"><span data-stu-id="3a427-107">In this walkthrough, you will create a simple `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="3a427-108">Anschließend rufen Sie die Daten aus der Datei ab, wenn Sie das Objekt neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a427-108">You will then retrieve the data from the file when you re-create the object.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3a427-109">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3a427-109">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="3a427-110">Wenn eine Anwendung eine Datei erstellen muss, muss Sie über die `Create`-Berechtigung für den Ordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="3a427-110">If an application must create a file, that application must `Create` permission for the folder.</span></span> <span data-ttu-id="3a427-111">Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3a427-111">Permissions are set by using access control lists.</span></span> <span data-ttu-id="3a427-112">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung `Write`, was einer geringeren Berechtigung entspricht.</span><span class="sxs-lookup"><span data-stu-id="3a427-112">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="3a427-113">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte die `Read`-Berechtigung nur für eine einzelne Datei erteilt werden (anstatt „Create“-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="3a427-113">Where possible, it is more secure to create the file during deployment, and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="3a427-114">Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programme“ zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3a427-114">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3a427-115">In diesem Beispiel werden Daten in einer Binärdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3a427-115">This example stores data in a binary.</span></span> <span data-ttu-id="3a427-116">Diese Formate sollten nicht für sensible Daten wie Kennwörter oder Kreditkarteninformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a427-116">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a427-117">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="3a427-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3a427-118">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a427-118">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3a427-119">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3a427-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-loan-object"></a><span data-ttu-id="3a427-120">Erstellen des Loan-Objekts</span><span class="sxs-lookup"><span data-stu-id="3a427-120">Creating the Loan Object</span></span>  
 <span data-ttu-id="3a427-121">Der erste Schritt ist das Erstellen einer `Loan`-Klasse und einer Testanwendung, die die Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a427-121">The first step is to create a `Loan` class and a test application that uses the class.</span></span>  
  
### <a name="to-create-the-loan-class"></a><span data-ttu-id="3a427-122">So erstellen Sie eine Loan-Klasse</span><span class="sxs-lookup"><span data-stu-id="3a427-122">To create the Loan class</span></span>  
  
1. <span data-ttu-id="3a427-123">Erstellen Sie ein neues Klassenbibliotheksprojekt mit dem Namen „LoanClass“.</span><span class="sxs-lookup"><span data-stu-id="3a427-123">Create a new Class Library project and name it "LoanClass".</span></span> <span data-ttu-id="3a427-124">Weitere Informationen finden Sie unter [Erstellen von Projekten und Projektmappen](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="3a427-124">For more information, see [Creating Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).</span></span>  
  
2. <span data-ttu-id="3a427-125">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für die Datei „Class1“ und wählen Sie **Umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="3a427-125">In **Solution Explorer**, open the shortcut menu for the Class1 file and choose **Rename**.</span></span> <span data-ttu-id="3a427-126">Benennen Sie die Datei in `Loan` um, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="3a427-126">Rename the file to `Loan` and press ENTER.</span></span> <span data-ttu-id="3a427-127">Durch Umbenennen der Datei wird die Klasse ebenfalls in `Loan` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="3a427-127">Renaming the file will also rename the class to `Loan`.</span></span>  
  
3. <span data-ttu-id="3a427-128">Fügen Sie der Klasse die folgenden öffentlichen Member hinzu:</span><span class="sxs-lookup"><span data-stu-id="3a427-128">Add the following public members to the class:</span></span>  
  
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
  
 <span data-ttu-id="3a427-129">Sie müssen ebenfalls eine einfache Anwendung erstellen, die die `Loan`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a427-129">You will also have to create a simple application that uses the `Loan` class.</span></span>  
  
### <a name="to-create-a-test-application"></a><span data-ttu-id="3a427-130">So erstellen Sie eine Testanwendung</span><span class="sxs-lookup"><span data-stu-id="3a427-130">To create a test application</span></span>  
  
1. <span data-ttu-id="3a427-131">Wählen Sie im Menü **Datei** die Optionen **Hinzufügen** und **Neues Projekt** aus, um Ihrer Projektmappe ein Windows Forms-Anwendungsprojekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a427-131">To add a Windows Forms Application project to your solution, on the **File** menu, choose **Add**,**New Project**.</span></span>  
  
2. <span data-ttu-id="3a427-132">Wählen Sie im Dialogfeld **Neues Projekt hinzufügen\*\*\*\*Windows Forms-Anwendung** aus, und geben Sie als Namen für das Projekt `LoanApp` ein. Klicken Sie anschließend auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3a427-132">In the **Add New Project** dialog box, choose **Windows Forms Application**, and enter `LoanApp` as the name of the project, and then click **OK** to close the dialog box.</span></span>  
  
3. <span data-ttu-id="3a427-133">Wählen Sie im **Projektmappen-Explorer** das LoanApp-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="3a427-133">In **Solution Explorer**, choose the LoanApp project.</span></span>  
  
4. <span data-ttu-id="3a427-134">Klicken Sie im Menü **Projekt** auf **Als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="3a427-134">On the **Project** menu, choose **Set as StartUp Project**.</span></span>  
  
5. <span data-ttu-id="3a427-135">Wählen Sie im Menü **Projekt** den Befehl **Verweis hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="3a427-135">On the **Project** menu, choose **Add Reference**.</span></span>  
  
6. <span data-ttu-id="3a427-136">Wählen Sie im Dialogfeld **Verweis hinzufügen** die Registerkarte **Projekte** und anschließend das LoanClass-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="3a427-136">In the **Add Reference** dialog box, choose the **Projects** tab and then choose the LoanClass project.</span></span>  
  
7. <span data-ttu-id="3a427-137">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3a427-137">Click **OK** to close the dialog box.</span></span>  
  
8. <span data-ttu-id="3a427-138">Fügen Sie dem Formular im Designer vier <xref:System.Windows.Forms.TextBox>-Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a427-138">In the designer, add four <xref:System.Windows.Forms.TextBox> controls to the form.</span></span>  
  
9. <span data-ttu-id="3a427-139">Fügen Sie im Code-Editor folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="3a427-139">In the Code Editor, add the following code:</span></span>  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
10. <span data-ttu-id="3a427-140">Fügen Sie dem Formular mithilfe des folgenden Codes einen Ereignishandler für das Ereignis `PropertyChanged` hinzu:</span><span class="sxs-lookup"><span data-stu-id="3a427-140">Add an event handler for the `PropertyChanged` event to the form by using the following code:</span></span>  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 <span data-ttu-id="3a427-141">Nun können Sie die Anwendung erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a427-141">At this point, you can build and run the application.</span></span> <span data-ttu-id="3a427-142">Beachten Sie, dass die Standardwerte aus der `Loan`-Klasse in den Textfeldern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3a427-142">Note that the default values from the `Loan` class appear in the text boxes.</span></span> <span data-ttu-id="3a427-143">Versuchen Sie, den Wert „Zinssatz“ von 7,5 zu 7,1 zu ändern, schließen Sie die Anwendung, und führen Sie sie erneut aus – der Wert wird auf den Standardwert 7,5 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3a427-143">Try to change the interest-rate value from 7.5 to 7.1, and then close the application and run it again—the value reverts to the default of 7.5.</span></span>  
  
 <span data-ttu-id="3a427-144">In der Praxis ändern sich Zinssätze regelmäßig, aber nicht unbedingt jedes Mal wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3a427-144">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="3a427-145">Es ist besser, den aktuellsten Zinssatz zwischen zwei Instanzen der Anwendung beizubehalten, anstatt den Benutzer den Zinssatz bei jeder Ausführung der Anwendung aktualisieren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="3a427-145">Rather than making the user update the interest rate every time that the application runs, it is better to preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="3a427-146">Im nächsten Schritt werden Sie durch Hinzufügen von Serialisierung zur Loan-Klasse genau das tun.</span><span class="sxs-lookup"><span data-stu-id="3a427-146">In the next step, you will do just that by adding serialization to the Loan class.</span></span>  
  
## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="3a427-147">Verwenden von Serialisierung zum Beibehalten des Objekts</span><span class="sxs-lookup"><span data-stu-id="3a427-147">Using Serialization to Persist the Object</span></span>  
 <span data-ttu-id="3a427-148">Sie müssen die Klasse zuerst mit dem Attribut `Serializable` markieren, um die Werte für die Loan-Klasse beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="3a427-148">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span>  
  
### <a name="to-mark-a-class-as-serializable"></a><span data-ttu-id="3a427-149">So markieren Sie eine Klasse als serialisierbar</span><span class="sxs-lookup"><span data-stu-id="3a427-149">To mark a class as serializable</span></span>  
  
- <span data-ttu-id="3a427-150">Ändern Sie die Klassendeklaration für die Loan-Klasse wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3a427-150">Change the class declaration for the Loan class as follows:</span></span>  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 <span data-ttu-id="3a427-151">Der Compiler wird vom Attribut `Serializable` darüber informiert, dass der Inhalt der Klasse in einer Datei beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="3a427-151">The `Serializable` attribute tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="3a427-152">Da das Ereignis `PropertyChanged` von einem Windows Form-Objekt behandelt wird, kann es nicht serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3a427-152">Because the `PropertyChanged` event is handled by a Windows Form object, it cannot be serialized.</span></span> <span data-ttu-id="3a427-153">Das Attribut `NonSerialized` kann dazu verwendet werden, Klassenmember zu markieren, die nicht beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3a427-153">The `NonSerialized` attribute can be used to mark class members that should not be persisted.</span></span>  
  
### <a name="to-prevent-a-member-from-being-serialized"></a><span data-ttu-id="3a427-154">So verhindern Sie, dass ein Member serialisiert wird</span><span class="sxs-lookup"><span data-stu-id="3a427-154">To prevent a member from being serialized</span></span>  
  
- <span data-ttu-id="3a427-155">Ändern Sie die Deklaration für das Ereignis `PropertyChanged` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3a427-155">Change the declaration for the `PropertyChanged` event as follows:</span></span>  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 <span data-ttu-id="3a427-156">Fügen Sie als nächstes den Serialisierungscode zur LoanApp-Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a427-156">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="3a427-157">Um die Klasse zu serialisieren und in eine Datei zu schreiben, verwenden Sie die Namespaces <xref:System.IO> und <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="3a427-157">In order to serialize the class and write it to a file, you will use the <xref:System.IO> and <xref:System.Xml.Serialization> namespaces.</span></span> <span data-ttu-id="3a427-158">Sie können Verweise zu den notwendigen Klassenbibliotheken hinzufügen, damit Sie die vollqualifizierten Namen nicht eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="3a427-158">To avoid typing the fully qualified names, you can add references to the necessary class libraries.</span></span>  
  
### <a name="to-add-references-to-namespaces"></a><span data-ttu-id="3a427-159">So fügen Sie Verweise zu Namespaces hinzu</span><span class="sxs-lookup"><span data-stu-id="3a427-159">To add references to namespaces</span></span>  
  
- <span data-ttu-id="3a427-160">Fügen Sie am Anfang der `Form1`-Klasse die folgenden Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="3a427-160">Add the following statements to the top of the `Form1` class:</span></span>  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     <span data-ttu-id="3a427-161">In diesem Fall verwenden Sie ein binäres Formatierungsprogramm, um ein Objekt im Binärformat zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3a427-161">In this case, you are using a binary formatter to save the object in a binary format.</span></span>  
  
 <span data-ttu-id="3a427-162">Fügen Sie als nächstes Code hinzu, um das Objekt aus der Datei zu deserialisieren wenn das Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3a427-162">The next step is to add code to deserialize the object from the file when the object is created.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="3a427-163">So deserialisieren Sie ein Objekt</span><span class="sxs-lookup"><span data-stu-id="3a427-163">To deserialize an object</span></span>  
  
1. <span data-ttu-id="3a427-164">Fügen Sie eine Konstante zur Klasse für den Dateinamen der serialisierten Daten hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a427-164">Add a constant to the class for the serialized data's file name.</span></span>  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2. <span data-ttu-id="3a427-165">Ändern Sie den Code der `Form1_Load`-Ereignisprozedur wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3a427-165">Modify the code in the `Form1_Load` event procedure as follows:</span></span>  
  
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
  
     <span data-ttu-id="3a427-166">Beachten Sie, dass Sie erst sicherstellen müssen, ob die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3a427-166">Note that you first must check that the file exists.</span></span> <span data-ttu-id="3a427-167">Wenn sie vorhanden ist, erstellen Sie eine <xref:System.IO.Stream>-Klasse zum Lesen der Binärdatei und eine <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Klasse zum Übersetzen der Datei.</span><span class="sxs-lookup"><span data-stu-id="3a427-167">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="3a427-168">Sie müssen ebenfalls vom Streamtyp in den Loan-Objekttyp konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3a427-168">You also need to convert from the stream type to the Loan object type.</span></span>  
  
 <span data-ttu-id="3a427-169">Als nächstes müssen Sie Code hinzufügen, um die in die Textfelder eingegebenen Daten in der `Loan`-Klasse zu speichern. Anschließend müssen Sie die Klasse in eine Datei serialisieren.</span><span class="sxs-lookup"><span data-stu-id="3a427-169">Next you must add code to save the data entered in the text boxes to the `Loan` class, and then you must serialize the class to a file.</span></span>  
  
### <a name="to-save-the-data-and-serialize-the-class"></a><span data-ttu-id="3a427-170">So speichern Sie die Daten und serialisieren die Klasse</span><span class="sxs-lookup"><span data-stu-id="3a427-170">To save the data and serialize the class</span></span>  
  
- <span data-ttu-id="3a427-171">Fügen Sie den folgenden Code zur `Form1_FormClosing`-Ereignisprozedur hinzu:</span><span class="sxs-lookup"><span data-stu-id="3a427-171">Add the following code to the `Form1_FormClosing` event procedure:</span></span>  
  
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
  
 <span data-ttu-id="3a427-172">Nun können Sie die Anwendung erneut erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a427-172">At this point, you can again build and run the application.</span></span> <span data-ttu-id="3a427-173">Zuerst werden die Standardwerte in den Textfeldern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a427-173">Initially, the default values appear in the text boxes.</span></span> <span data-ttu-id="3a427-174">Versuchen Sie, die Werte zu ändern, und geben Sie einen Namen in das vierte Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="3a427-174">Try to change the values and enter a name in the fourth text box.</span></span> <span data-ttu-id="3a427-175">Schließen Sie die Anwendung, und führen Sie sie dann erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3a427-175">Close the application and then run it again.</span></span> <span data-ttu-id="3a427-176">Beachten Sie, dass die neuen Werte jetzt in den Textfeldern erscheinen.</span><span class="sxs-lookup"><span data-stu-id="3a427-176">Note that the new values now appear in the text boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a427-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a427-177">See also</span></span>

- [<span data-ttu-id="3a427-178">Serialisierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a427-178">Serialization (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="3a427-179">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3a427-179">Visual Basic Programming Guide</span></span>](../../index.md)
