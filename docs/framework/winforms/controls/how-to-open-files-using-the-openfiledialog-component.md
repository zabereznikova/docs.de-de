---
title: 'Vorgehensweise: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 87e7640da76205341b9e95310314800ac9dbfe30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678810"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a><span data-ttu-id="beac4-102">Vorgehensweise: Öffnen von Dateien mit der OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="beac4-102">How to: Open Files Using the OpenFileDialog Component</span></span>
<span data-ttu-id="beac4-103">Die <xref:System.Windows.Forms.OpenFileDialog> -Komponente können Benutzer die Ordner von ihrem Computer oder einem beliebigen Computer im Netzwerk durchsuchen, und wählen Sie eine oder mehrere Dateien zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="beac4-103">The <xref:System.Windows.Forms.OpenFileDialog> component allows users to browse the folders of their computer or any computer on the network and select one or more files to open.</span></span> <span data-ttu-id="beac4-104">Das Dialogfeld gibt den Pfad und den Namen der ausgewählten Datei zurück.</span><span class="sxs-lookup"><span data-stu-id="beac4-104">The dialog box returns the path and name of the file the user selected in the dialog box.</span></span>  
  
 <span data-ttu-id="beac4-105">Sobald der Benutzer die Datei ausgewählt hat, die geöffnet werden soll, gibt es zwei Möglichkeiten zum Öffnen der Datei.</span><span class="sxs-lookup"><span data-stu-id="beac4-105">Once the user has selected the file to be opened, there are two approaches to the mechanism of opening the file.</span></span> <span data-ttu-id="beac4-106">Wenn Sie mit Dateistreams arbeiten bevorzugt, können Sie erstellen eine Instanz von der <xref:System.IO.StreamReader> Klasse.</span><span class="sxs-lookup"><span data-stu-id="beac4-106">If you prefer to work with file streams, you can create an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="beac4-107">Sie können auch mithilfe der <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode, um die ausgewählte Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="beac4-107">Alternately, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the selected file.</span></span>  
  
 <span data-ttu-id="beac4-108">Das erste Beispiel unten beinhaltet einen <xref:System.Security.Permissions.FileIOPermission> berechtigungsüberprüfung (wie in "Sicherheitshinweis" weiter unten beschrieben), jedoch erhalten Sie Zugriff auf den Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="beac4-108">The first example below involves a <xref:System.Security.Permissions.FileIOPermission> permission check (as described in the "Security Note" below), but gives you access to the filename.</span></span> <span data-ttu-id="beac4-109">Diese Vorgehensweise können Sie in den Zonen „Lokaler Computer“, „Intranet“ und „Internet“ befolgen.</span><span class="sxs-lookup"><span data-stu-id="beac4-109">You can use this technique from the Local Machine, Intranet, and Internet zones.</span></span> <span data-ttu-id="beac4-110">Die zweite Methode ist, auch ein <xref:System.Security.Permissions.FileIOPermission> berechtigungsüberprüfung, allerdings eignet sich besser für Anwendungen, die in den Zonen Intranet oder Internet.</span><span class="sxs-lookup"><span data-stu-id="beac4-110">The second method also does a <xref:System.Security.Permissions.FileIOPermission> permission check, but is better suited for applications in the Intranet or Internet zones.</span></span>  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a><span data-ttu-id="beac4-111">So öffnen Sie eine Datei mit der OpenFileDialog-Komponente als Stream</span><span class="sxs-lookup"><span data-stu-id="beac4-111">To open a file as a stream using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="beac4-112">Zeigen Sie das Dialogfeld **Datei öffnen** an, und rufen Sie eine Methode zum Öffnen der vom Benutzer ausgewählten Datei auf.</span><span class="sxs-lookup"><span data-stu-id="beac4-112">Display the **Open File** dialog box and call a method to open the file selected by the user.</span></span>  
  
     <span data-ttu-id="beac4-113">Ein Ansatz ist die Verwendung der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode zum Anzeigen des Dialogfelds Datei öffnen, und verwenden eine Instanz von der <xref:System.IO.StreamReader> Klasse, um die Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="beac4-113">One approach is to use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the Open File dialog box, and use an instance of the <xref:System.IO.StreamReader> class to open the file.</span></span>  
  
     <span data-ttu-id="beac4-114">Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler zum Öffnen einer Instanz von der <xref:System.Windows.Forms.OpenFileDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="beac4-114">The example below uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open an instance of the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="beac4-115">Wenn eine Datei ausgewählt wird und der Benutzer auf **OK** klickt, wird die im Dialogfeld markierte Datei geöffnet.</span><span class="sxs-lookup"><span data-stu-id="beac4-115">When a file is chosen and the user clicks **OK**, the file selected in the dialog box opens.</span></span> <span data-ttu-id="beac4-116">In diesem Fall wird der Inhalt in einem Meldungsfeld angezeigt, um darüber zu informieren, dass der Dateistream gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="beac4-116">In this case, the contents are displayed in a message box, just to show that the file stream has been read.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="beac4-117">Zum Abrufen oder Festlegen der <xref:System.Windows.Forms.FileDialog.FileName%2A> -Eigenschaft muss die Assembly eine Berechtigungsebene gewährt durch die <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="beac4-117">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="beac4-118">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="beac4-118">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="beac4-119">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="beac4-119">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="beac4-120">Im Beispiel wird vorausgesetzt, das Formular enthält ein <xref:System.Windows.Forms.Button> Steuerelement und ein <xref:System.Windows.Forms.OpenFileDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="beac4-120">The example assumes your form has a <xref:System.Windows.Forms.Button> control and an <xref:System.Windows.Forms.OpenFileDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     <span data-ttu-id="beac4-121">(Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="beac4-121">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="beac4-122">Weitere Informationen zum Lesen aus Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginRead%2A> und <xref:System.IO.FileStream.Read%2A>.</span><span class="sxs-lookup"><span data-stu-id="beac4-122">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A> and <xref:System.IO.FileStream.Read%2A>.</span></span>  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a><span data-ttu-id="beac4-123">So öffnen Sie eine Datei mit der OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="beac4-123">To open a file as a file using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="beac4-124">Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld anzuzeigen und die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode, um die Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="beac4-124">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the file.</span></span>  
  
     <span data-ttu-id="beac4-125">Die <xref:System.Windows.Forms.OpenFileDialog> Komponente <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methodenrückgabe die Bytes, die die Datei besteht.</span><span class="sxs-lookup"><span data-stu-id="beac4-125">The <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method returns the bytes that compose the file.</span></span> <span data-ttu-id="beac4-126">Diese Bytes bilden einen Stream, aus dem Sie Daten lesen können.</span><span class="sxs-lookup"><span data-stu-id="beac4-126">These bytes give you a stream to read from.</span></span> <span data-ttu-id="beac4-127">Im folgenden Beispiel wird ein <xref:System.Windows.Forms.OpenFileDialog> Komponente instanziiert wird, mit einem Filter "Cursor", damit der Benutzer wählen Sie nur Dateien mit der Dateinamenerweiterung`.cur`.</span><span class="sxs-lookup"><span data-stu-id="beac4-127">In the example below, an <xref:System.Windows.Forms.OpenFileDialog> component is instantiated with a "cursor" filter on it, allowing the user to choose only files with the file name extension`.cur`.</span></span> <span data-ttu-id="beac4-128">Bei Wahl einer `.cur`-Datei wird der Cursor in der ausgewählten Form angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beac4-128">If a`.cur` file is chosen, the form's cursor is set to the selected cursor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="beac4-129">Zum Aufrufen der <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> -Methode, muss die Assembly eine Berechtigungsebene gewährt durch die <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="beac4-129">To call the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="beac4-130">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="beac4-130">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="beac4-131">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="beac4-131">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="beac4-132">Im Beispiel wird vorausgesetzt, das Formular enthält ein <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="beac4-132">The example assumes your form has a <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     <span data-ttu-id="beac4-133">(Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="beac4-133">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="beac4-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beac4-134">See also</span></span>
- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="beac4-135">OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="beac4-135">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
