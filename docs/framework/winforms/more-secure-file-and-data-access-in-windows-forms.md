---
title: Sicherere Datei-und Datenzugriff
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
ms.openlocfilehash: 49ba1919f68f35e9d72b012540b785e05c307c39
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743748"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="871bb-102">Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="871bb-102">More Secure File and Data Access in Windows Forms</span></span>
<span data-ttu-id="871bb-103">Der .NET Framework verwendet Berechtigungen zum Schützen von Ressourcen und Daten.</span><span class="sxs-lookup"><span data-stu-id="871bb-103">The .NET Framework uses permissions to help protect resources and data.</span></span> <span data-ttu-id="871bb-104">In welchen Situationen Daten von einer Anwendung gelesen oder geschrieben werden können, hängt davon ab, welche Berechtigungen der Anwendung gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="871bb-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="871bb-105">Wenn die Anwendung in einer Umgebung mit teilweiser Vertrauenswürdigkeit ausgeführt wird, können Sie unter Umständen auf bestimmte Daten nicht zugreifen oder müssen die Art des Zugriffs auf bestimmte Daten ändern.</span><span class="sxs-lookup"><span data-stu-id="871bb-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="871bb-106">Wenn eine Sicherheitseinschränkung auftritt, haben Sie zwei Möglichkeiten: Sie können die Berechtigung bestätigen (in der Annahme, dass diese der Anwendung gewährt wurde), oder Sie verwenden eine Version des Features, die für die Ausführung mit teilweiser Vertrauenswürdigkeit geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="871bb-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="871bb-107">In den folgenden Abschnitten wird der Zugriff auf Dateien, Datenbanken und die Registrierung aus Anwendungen erläutert, die in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="871bb-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="871bb-108">Standardmäßig verfügen Tools, die ClickOnce-bereit Stellungen generieren, standardmäßig über diese bereit Stellungen, um die volle Vertrauenswürdigkeit von den Computern anzufordern, auf denen Sie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="871bb-108">By default, tools that generate ClickOnce deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="871bb-109">Wenn Sie die zusätzlichen Sicherheitsvorteile der Ausführung mit teilweiser Vertrauenswürdigkeit festlegen möchten, müssen Sie diese Standardeinstellung entweder in Visual Studio oder in einem der Windows SDK Tools ("Mage. exe" oder "MageUI. exe") ändern.</span><span class="sxs-lookup"><span data-stu-id="871bb-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either Visual Studio or one of the Windows SDK tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="871bb-110">Weitere Informationen zur Windows Forms Sicherheit und zum Ermitteln der entsprechenden Vertrauens Ebene für Ihre Anwendung finden Sie unter [Sicherheit in Windows Forms Übersicht](security-in-windows-forms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="871bb-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="871bb-111">Dateizugriff</span><span class="sxs-lookup"><span data-stu-id="871bb-111">File Access</span></span>  
 <span data-ttu-id="871bb-112">Die <xref:System.Security.Permissions.FileIOPermission>-Klasse steuert den Zugriff auf Dateien und Ordner im .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="871bb-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the .NET Framework.</span></span> <span data-ttu-id="871bb-113">Standardmäßig gewährt das Sicherheitssystem teilweise vertrauenswürdigen Umgebungen wie der lokalen Intranetzone oder der Internetzone keine <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="871bb-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="871bb-114">Eine Anwendung, die Dateizugriff erfordert, kann in diesen Umgebungen dennoch ausgeführt werden, wenn Sie sie ändern oder andere Methoden für den Zugriff auf Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="871bb-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="871bb-115">Standardmäßig wird der lokalen Intranetzone die Berechtigung gewährt, auf dieselbe Site und dasselbe Verzeichnis zuzugreifen, die Verbindung mit der Ursprungssite wiederherzustellen und Daten im Installationsverzeichnis zu lesen.</span><span class="sxs-lookup"><span data-stu-id="871bb-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="871bb-116">Der Internetzone wird in der Standardeinstellung nur die Berechtigung gewährt, die Verbindung mit der Ursprungssite wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="871bb-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="871bb-117">Benutzerdefinierte Dateien</span><span class="sxs-lookup"><span data-stu-id="871bb-117">User-Specified Files</span></span>  
 <span data-ttu-id="871bb-118">Wenn keine Dateizugriffsberechtigung vorliegt, können Sie z. B. den Benutzer mithilfe der <xref:System.Windows.Forms.OpenFileDialog>-Klasse oder der <xref:System.Windows.Forms.SaveFileDialog>-Klasse auffordern, bestimmte Dateiinformationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="871bb-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="871bb-119">Durch diese Interaktion mit dem Benutzer soll verhindert werden, dass die Anwendung in böser Absicht vertrauliche Dateien lädt oder wichtige Dateien überschreibt.</span><span class="sxs-lookup"><span data-stu-id="871bb-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="871bb-120">Die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>-Methode und die <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>-Methode ermöglichen den Lese- und Schreibzugriff durch Öffnen des vom Benutzer für die Datei angegebenen Dateistreams.</span><span class="sxs-lookup"><span data-stu-id="871bb-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="871bb-121">Diese Methoden dienen ebenfalls dem Schutz der Datei des Benutzers, indem der Dateipfad verdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="871bb-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="871bb-122">Diese Berechtigungen unterscheiden sich in Abhängigkeit davon, ob die Anwendung in der Internetzone oder der Intranetzone ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="871bb-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="871bb-123">Anwendungen für die Internetzone können nur <xref:System.Windows.Forms.OpenFileDialog> verwenden. Intranetanwendungen verfügen hingegen über uneingeschränkte Berechtigungen für Dateidialogfelder.</span><span class="sxs-lookup"><span data-stu-id="871bb-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="871bb-124">Durch die <xref:System.Security.Permissions.FileDialogPermission>-Klasse wird angegeben, welcher Typ von Dateidialogfeld von der Anwendung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="871bb-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="871bb-125">In der folgenden Tabelle sind die Werte aufgeführt, die für die Verwendung der einzelnen <xref:System.Windows.Forms.FileDialog>-Klassen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="871bb-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="871bb-126">Klasse</span><span class="sxs-lookup"><span data-stu-id="871bb-126">Class</span></span>|<span data-ttu-id="871bb-127">Erforderlicher Zugriffswert</span><span class="sxs-lookup"><span data-stu-id="871bb-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
> <span data-ttu-id="871bb-128">Die jeweilige Berechtigung wird erst angefordert, wenn die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="871bb-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="871bb-129">Die Berechtigung zum Anzeigen eines Dateidialogfelds gewährt der Anwendung keinen vollständigen Zugriff auf alle Member der Klassen <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="871bb-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="871bb-130">Die genauen Berechtigungen, die erforderlich sind, um die einzelnen Methoden aufzurufen, finden Sie im Referenz Thema für diese Methode in der Dokumentation zur .NET Framework-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="871bb-130">For the exact permissions that are required to call each method, see the reference topic for that method in the .NET Framework class library documentation.</span></span>  
  
 <span data-ttu-id="871bb-131">Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>-Methode zum Öffnen einer benutzerdefinierten Datei in einem <xref:System.Windows.Forms.RichTextBox>-Steuerelement verwendet.</span><span class="sxs-lookup"><span data-stu-id="871bb-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="871bb-132">Für dieses Beispiel sind <xref:System.Security.Permissions.FileDialogPermission> und der zugehörige <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A>-Enumerationswert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="871bb-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="871bb-133">In diesem Beispiel wird gezeigt, wie mit der <xref:System.Security.SecurityException> ermittelt werden kann, ob die Speicherfunktion deaktiviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="871bb-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="871bb-134">Für dieses Beispiel ist es erforderlich, dass <xref:System.Windows.Forms.Form> über ein <xref:System.Windows.Forms.Button>-Steuerelement mit dem Namen `ButtonOpen` und ein <xref:System.Windows.Forms.RichTextBox>-Steuerelement mit dem Namen `RtfBoxMain` verfügt.</span><span class="sxs-lookup"><span data-stu-id="871bb-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="871bb-135">Die Programmierlogik für die Speicherfunktion ist im Beispiel nicht dargestellt.</span><span class="sxs-lookup"><span data-stu-id="871bb-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click   
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try   
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()   
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try   
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then   
                ' The application does not have unrestricted permission   
                ' to the file so the save feature will be disabled.  
                saveAllowed = False   
            Else   
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)   
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)   
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())   
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try   
        {  
            editingFileName = openFileDialog1.FileName;  
        }   
        catch (Exception ex)   
        {  
            if (ex is System.Security.SecurityException)   
            {  
                // The application does not have unrestricted permission   
                // to the file so the save feature will be disabled.  
                saveAllowed = false;   
            }   
            else   
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="871bb-136">Stellen Sie C#in Visual sicher, dass Sie Code hinzufügen, um den Ereignishandler zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="871bb-136">In Visual C#, ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="871bb-137">Im folgenden Code wird unter Verwendung des obigen Codebeispiels der Ereignishandler aktiviert: `this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span><span class="sxs-lookup"><span data-stu-id="871bb-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="871bb-138">Andere Dateien</span><span class="sxs-lookup"><span data-stu-id="871bb-138">Other Files</span></span>  
 <span data-ttu-id="871bb-139">Gelegentlich müssen Sie Dateien lesen oder in Dateien schreiben, die der Benutzer nicht angibt, beispielsweise beim Speichern von Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="871bb-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="871bb-140">In der lokalen Intranetzone und der Internetzone haben Anwendungen keine Berechtigung zum Speichern von Daten in einer lokalen Datei.</span><span class="sxs-lookup"><span data-stu-id="871bb-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="871bb-141">Die Anwendung jedoch Daten in isoliertem Speicher ablegen.</span><span class="sxs-lookup"><span data-stu-id="871bb-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="871bb-142">Der isolierte Speicher ist ein abstraktes Datendepot (kein bestimmter Speicherort), das aus einer oder mehreren isolierten Speicherdateien, so genannten Speichern, besteht. Diese Speicher enthalten die tatsächlichen Speicherorte der Verzeichnisse, in denen Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="871bb-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="871bb-143">Berechtigungen für den Dateizugriff wie <xref:System.Security.Permissions.FileIOPermission> sind nicht erforderlich. Stattdessen werden die Berechtigungen für isolierten Speicher von der <xref:System.Security.Permissions.IsolatedStoragePermission>-Klasse gesteuert.</span><span class="sxs-lookup"><span data-stu-id="871bb-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="871bb-144">Standardmäßig können Anwendungen, die in der lokalen Intranetzone oder der Internetzone ausgeführt werden, Daten mithilfe des isolierten Speichers ablegen. Einstellungen wie das Datenträgerkontingent können jedoch variieren.</span><span class="sxs-lookup"><span data-stu-id="871bb-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="871bb-145">Weitere Informationen zu isoliertem Speicher finden Sie unter [isolierter Speicher](../../standard/io/isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="871bb-145">For more information about isolated storage, see [Isolated Storage](../../standard/io/isolated-storage.md).</span></span>  
  
 <span data-ttu-id="871bb-146">Im folgenden Beispiel wird der isolierte Speicher dazu verwendet, Daten in eine Datei in einem Speicher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="871bb-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="871bb-147">Für dieses Beispiel sind <xref:System.Security.Permissions.IsolatedStorageFilePermission> und der <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>-Enumerationswert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="871bb-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="871bb-148">In diesem Beispiel wird das Lesen und Schreiben bestimmter Eigenschaftswerte des <xref:System.Windows.Forms.Button>-Steuerelements in einer Datei im isolierten Speicher gezeigt.</span><span class="sxs-lookup"><span data-stu-id="871bb-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="871bb-149">Die `Read`-Funktion wird nach dem Starten der Anwendung aufgerufen, und die `Write`-Funktion vor dem Beenden der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="871bb-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="871bb-150">Das Beispiel setzt voraus, dass die Funktionen `Read` und `Write` als Member eines <xref:System.Windows.Forms.Form> vorhanden sind, das ein <xref:System.Windows.Forms.Button> Steuerelement mit dem Namen `MainButton`enthält.</span><span class="sxs-lookup"><span data-stu-id="871bb-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values   
' for the button if the options file does not exist.  
Public Sub Read()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try   
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _   
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try   
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try   
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _   
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _   
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values   
// for the button if the options file does not exist.  
public void Read()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =   
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try   
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =   
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {   
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }   
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try   
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try   
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new   
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,   
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {   
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="871bb-151">Datenbankzugriff</span><span class="sxs-lookup"><span data-stu-id="871bb-151">Database Access</span></span>  
 <span data-ttu-id="871bb-152">Die für den Zugriff auf eine Datenbank erforderlichen Berechtigungen hängen jeweils vom Datenbankanbieter ab. Jedoch können nur Anwendungen, die mit den entsprechenden Berechtigungen ausgeführt werden, über eine Datenverbindung auf eine Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="871bb-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="871bb-153">Weitere Informationen zu den Berechtigungen, die für den Zugriff auf eine Datenbank erforderlich sind, finden Sie unter [Code Zugriffssicherheit und ADO.net](../data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="871bb-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](../data/adonet/code-access-security.md).</span></span>  
  
 <span data-ttu-id="871bb-154">Wenn Sie nicht direkt auf eine Datenbank zugreifen können, da Sie die Anwendung nur mit teilweiser Vertrauenswürdigkeit ausführen möchten, können Sie auf die Daten auch über einen Webdienst zugreifen.</span><span class="sxs-lookup"><span data-stu-id="871bb-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="871bb-155">Ein Webdienst ist eine Softwarekomponente, auf die über ein Netzwerk programmgesteuert zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="871bb-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="871bb-156">Mit Webdiensten können Anwendungen Daten über Codegruppenzonen hinweg gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="871bb-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="871bb-157">Anwendungen in der lokalen Intranetzone und der Internetzone wird standardmäßig die Berechtigung gewährt, auf ihre Ursprungssite zuzugreifen. Dadurch sind diese Anwendungen in der Lage, auf demselben Server gehostete Webdienste aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="871bb-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="871bb-158">Weitere Informationen finden Sie [unter Webdienste in ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) oder [Windows Communication Foundation](../wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="871bb-158">For more information see [Web Services in ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) or [Windows Communication Foundation](../wcf/index.md).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="871bb-159">Zugriff auf die Registrierung</span><span class="sxs-lookup"><span data-stu-id="871bb-159">Registry Access</span></span>  
 <span data-ttu-id="871bb-160">Durch die <xref:System.Security.Permissions.RegistryPermission>-Klasse wird der Zugriff auf die Registrierung des Betriebssystems gesteuert.</span><span class="sxs-lookup"><span data-stu-id="871bb-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="871bb-161">Standardmäßig haben nur lokal ausgeführte Anwendungen Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="871bb-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="871bb-162">Durch <xref:System.Security.Permissions.RegistryPermission> wird einer Anwendung nur die Berechtigung gewährt, den Versuch zu unternehmen, auf die Registrierung zuzugreifen. Ein erfolgreicher Zugriff wird dadurch nicht garantiert, da das Betriebssystem immer noch die Einhaltung von Sicherheitsrichtlinien für die Registrierung erzwingt.</span><span class="sxs-lookup"><span data-stu-id="871bb-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="871bb-163">Da bei teilweiser Vertrauenswürdigkeit nicht auf die Registrierung zugegriffen werden kann, müssen Sie unter Umständen einen anderen Weg zum Speichern Ihrer Daten finden.</span><span class="sxs-lookup"><span data-stu-id="871bb-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="871bb-164">Verwenden Sie beim Speichern von Anwendungseinstellungen anstelle der Registrierung den isolierten Speicher.</span><span class="sxs-lookup"><span data-stu-id="871bb-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="871bb-165">Der isolierte Speicher kann auch zum Speichern anderer anwendungsspezifischer Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="871bb-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="871bb-166">Ebenso können Sie globale Anwendungsinformationen zum Server oder zur Ursprungssite speichern, da Anwendungen standardmäßig berechtigt sind, auf die Ursprungssite zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="871bb-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="871bb-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="871bb-167">See also</span></span>

- [<span data-ttu-id="871bb-168">Mehr Sicherheit beim Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="871bb-168">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)
- [<span data-ttu-id="871bb-169">Weitere Überlegungen zur Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="871bb-169">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="871bb-170">Übersicht über die Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="871bb-170">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="871bb-171">Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="871bb-171">Windows Forms Security</span></span>](windows-forms-security.md)
- [<span data-ttu-id="871bb-172">Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)</span><span class="sxs-lookup"><span data-stu-id="871bb-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../tools/mage-exe-manifest-generation-and-editing-tool.md)
- [<span data-ttu-id="871bb-173">MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)</span><span class="sxs-lookup"><span data-stu-id="871bb-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
