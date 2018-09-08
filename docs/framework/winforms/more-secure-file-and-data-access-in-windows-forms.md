---
title: Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms
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
ms.openlocfilehash: d5a9b08188e346fdea5b155149dee1ef8368c2a0
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183849"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a>Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms
In [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] werden Berechtigungen zum Schutz von Ressourcen und Daten verwendet. In welchen Situationen Daten von einer Anwendung gelesen oder geschrieben werden können, hängt davon ab, welche Berechtigungen der Anwendung gewährt wurden. Wenn die Anwendung in einer Umgebung mit teilweiser Vertrauenswürdigkeit ausgeführt wird, können Sie unter Umständen auf bestimmte Daten nicht zugreifen oder müssen die Art des Zugriffs auf bestimmte Daten ändern.  
  
 Wenn eine Sicherheitseinschränkung auftritt, haben Sie zwei Möglichkeiten: Sie können die Berechtigung bestätigen (in der Annahme, dass diese der Anwendung gewährt wurde), oder Sie verwenden eine Version des Features, die für die Ausführung mit teilweiser Vertrauenswürdigkeit geschrieben wurde. In den folgenden Abschnitten wird der Zugriff auf Dateien, Datenbanken und die Registrierung aus Anwendungen erläutert, die in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden.  
  
> [!NOTE]
>  Standardmäßig werden [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]-Bereitstellungen von den entsprechenden Tools so generiert, dass diese auf den Computern , auf denen sie ausgeführt werden, volle Vertrauenswürdigkeit anfordern. Wenn Sie sich entscheiden, Sie möchten die Vorteile der Erhöhung der Sicherheit bei teilweiser Vertrauenswürdigkeit ausführen, müssen Sie diese Standardeinstellung in Visual Studio oder über eine der Ändern der [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] -Tools (Mage.exe oder MageUI.exe). Weitere Informationen zur Sicherheit in Windows Forms und festlegen, um zu bestimmen, für Ihre Anwendung geeigneten Vertrauensebene finden Sie unter [Sicherheit in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md).  
  
## <a name="file-access"></a>Dateizugriff  
 Der Zugriff auf Dateien und Ordner wird in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] über die <xref:System.Security.Permissions.FileIOPermission>-Klasse gesteuert. Standardmäßig gewährt das Sicherheitssystem teilweise vertrauenswürdigen Umgebungen wie der lokalen Intranetzone oder der Internetzone keine <xref:System.Security.Permissions.FileIOPermission>. Eine Anwendung, die Dateizugriff erfordert, kann in diesen Umgebungen dennoch ausgeführt werden, wenn Sie sie ändern oder andere Methoden für den Zugriff auf Dateien verwenden. Standardmäßig wird der lokalen Intranetzone die Berechtigung gewährt, auf dieselbe Site und dasselbe Verzeichnis zuzugreifen, die Verbindung mit der Ursprungssite wiederherzustellen und Daten im Installationsverzeichnis zu lesen. Der Internetzone wird in der Standardeinstellung nur die Berechtigung gewährt, die Verbindung mit der Ursprungssite wiederherzustellen.  
  
### <a name="user-specified-files"></a>Benutzerdefinierte Dateien  
 Wenn keine Dateizugriffsberechtigung vorliegt, können Sie z. B. den Benutzer mithilfe der <xref:System.Windows.Forms.OpenFileDialog>-Klasse oder der <xref:System.Windows.Forms.SaveFileDialog>-Klasse auffordern, bestimmte Dateiinformationen bereitzustellen. Durch diese Interaktion mit dem Benutzer soll verhindert werden, dass die Anwendung in böser Absicht vertrauliche Dateien lädt oder wichtige Dateien überschreibt. Die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>-Methode und die <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>-Methode ermöglichen den Lese- und Schreibzugriff durch Öffnen des vom Benutzer für die Datei angegebenen Dateistreams. Diese Methoden dienen ebenfalls dem Schutz der Datei des Benutzers, indem der Dateipfad verdeckt wird.  
  
> [!NOTE]
>  Diese Berechtigungen unterscheiden sich in Abhängigkeit davon, ob die Anwendung in der Internetzone oder der Intranetzone ausgeführt wird. Anwendungen für die Internetzone können nur <xref:System.Windows.Forms.OpenFileDialog> verwenden. Intranetanwendungen verfügen hingegen über uneingeschränkte Berechtigungen für Dateidialogfelder.  
  
 Durch die <xref:System.Security.Permissions.FileDialogPermission>-Klasse wird angegeben, welcher Typ von Dateidialogfeld von der Anwendung verwendet werden kann. In der folgenden Tabelle sind die Werte aufgeführt, die für die Verwendung der einzelnen <xref:System.Windows.Forms.FileDialog>-Klassen erforderlich sind.  
  
|Klasse|Erforderlicher Zugriffswert|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
>  Die jeweilige Berechtigung wird erst angefordert, wenn die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>-Methode aufgerufen wird.  
  
 Die Berechtigung zum Anzeigen eines Dateidialogfelds gewährt der Anwendung keinen vollständigen Zugriff auf alle Member der Klassen <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog>. Die genauen Berechtigungen, die zum Aufrufen der einzelnen Methoden erforderlich sind, finden Sie im Referenzthema der jeweiligen Methode in der Dokumentation zur [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Klassenbibliothek.  
  
 Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>-Methode zum Öffnen einer benutzerdefinierten Datei in einem <xref:System.Windows.Forms.RichTextBox>-Steuerelement verwendet. Für dieses Beispiel sind <xref:System.Security.Permissions.FileDialogPermission> und der zugehörige <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A>-Enumerationswert erforderlich. In diesem Beispiel wird gezeigt, wie mit der <xref:System.Security.SecurityException> ermittelt werden kann, ob die Speicherfunktion deaktiviert werden sollte. Für dieses Beispiel ist es erforderlich, dass <xref:System.Windows.Forms.Form> über ein <xref:System.Windows.Forms.Button>-Steuerelement mit dem Namen `ButtonOpen` und ein <xref:System.Windows.Forms.RichTextBox>-Steuerelement mit dem Namen `RtfBoxMain` verfügt.  
  
> [!NOTE]
>  Die Programmierlogik für die Speicherfunktion ist im Beispiel nicht dargestellt.  
  
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
>  In Visual C#-, stellen Sie sicher, dass Sie Code zum Aktivieren des ereignishandlers hinzufügen. Im folgenden Code wird unter Verwendung des obigen Codebeispiels der Ereignishandler aktiviert: `this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`  
  
### <a name="other-files"></a>Weitere Dateien  
 Gelegentlich müssen Sie Dateien lesen oder in Dateien schreiben, die der Benutzer nicht angibt, beispielsweise beim Speichern von Anwendungseinstellungen. In der lokalen Intranetzone und der Internetzone haben Anwendungen keine Berechtigung zum Speichern von Daten in einer lokalen Datei. Die Anwendung jedoch Daten in isoliertem Speicher ablegen. Der isolierte Speicher ist ein abstraktes Datendepot (kein bestimmter Speicherort), das aus einer oder mehreren isolierten Speicherdateien, so genannten Speichern, besteht. Diese Speicher enthalten die tatsächlichen Speicherorte der Verzeichnisse, in denen Daten gespeichert werden. Berechtigungen für den Dateizugriff wie <xref:System.Security.Permissions.FileIOPermission> sind nicht erforderlich. Stattdessen werden die Berechtigungen für isolierten Speicher von der <xref:System.Security.Permissions.IsolatedStoragePermission>-Klasse gesteuert. Standardmäßig können Anwendungen, die in der lokalen Intranetzone oder der Internetzone ausgeführt werden, Daten mithilfe des isolierten Speichers ablegen. Einstellungen wie das Datenträgerkontingent können jedoch variieren. Weitere Informationen zum isolierten Speicher finden Sie unter [isolierten Speicher](../../../docs/standard/io/isolated-storage.md).  
  
 Im folgenden Beispiel wird der isolierte Speicher dazu verwendet, Daten in eine Datei in einem Speicher zu schreiben. Für dieses Beispiel sind <xref:System.Security.Permissions.IsolatedStorageFilePermission> und der <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>-Enumerationswert erforderlich. In diesem Beispiel wird das Lesen und Schreiben bestimmter Eigenschaftswerte des <xref:System.Windows.Forms.Button>-Steuerelements in einer Datei im isolierten Speicher gezeigt. Die `Read`-Funktion wird nach dem Starten der Anwendung aufgerufen, und die `Write`-Funktion vor dem Beenden der Anwendung. Im Beispiel erfordert, dass der `Read` und `Write` Funktionen vorhanden sind, als Mitglied einer <xref:System.Windows.Forms.Form> , enthält eine <xref:System.Windows.Forms.Button> Steuerelement mit dem Namen `MainButton`.  
  
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
  
## <a name="database-access"></a>Datenbankzugriff  
 Die für den Zugriff auf eine Datenbank erforderlichen Berechtigungen hängen jeweils vom Datenbankanbieter ab. Jedoch können nur Anwendungen, die mit den entsprechenden Berechtigungen ausgeführt werden, über eine Datenverbindung auf eine Datenbank zugreifen. Weitere Informationen zu den Berechtigungen, die Zugriff auf eine Datenbank erforderlich sind, finden Sie unter [Codezugriffssicherheit und ADO.NET](../../../docs/framework/data/adonet/code-access-security.md).  
  
 Wenn Sie nicht direkt auf eine Datenbank zugreifen können, da Sie die Anwendung nur mit teilweiser Vertrauenswürdigkeit ausführen möchten, können Sie auf die Daten auch über einen Webdienst zugreifen. Ein Webdienst ist eine Softwarekomponente, auf die über ein Netzwerk programmgesteuert zugegriffen werden kann. Mit Webdiensten können Anwendungen Daten über Codegruppenzonen hinweg gemeinsam verwenden. Anwendungen in der lokalen Intranetzone und der Internetzone wird standardmäßig die Berechtigung gewährt, auf ihre Ursprungssite zuzugreifen. Dadurch sind diese Anwendungen in der Lage, auf demselben Server gehostete Webdienste aufzurufen. Weitere Informationen finden Sie unter [Webdienste in ASP.NET AJAX](https://msdn.microsoft.com/library/8290e543-7eff-47a4-aace-681f3c07229b) oder [Windows Communication Foundation](https://msdn.microsoft.com/library/ms735119.aspx).  
  
## <a name="registry-access"></a>Zugriff auf die Registrierung  
 Durch die <xref:System.Security.Permissions.RegistryPermission>-Klasse wird der Zugriff auf die Registrierung des Betriebssystems gesteuert. Standardmäßig haben nur lokal ausgeführte Anwendungen Zugriff auf die Registrierung.  Durch <xref:System.Security.Permissions.RegistryPermission> wird einer Anwendung nur die Berechtigung gewährt, den Versuch zu unternehmen, auf die Registrierung zuzugreifen. Ein erfolgreicher Zugriff wird dadurch nicht garantiert, da das Betriebssystem immer noch die Einhaltung von Sicherheitsrichtlinien für die Registrierung erzwingt.  
  
 Da bei teilweiser Vertrauenswürdigkeit nicht auf die Registrierung zugegriffen werden kann, müssen Sie unter Umständen einen anderen Weg zum Speichern Ihrer Daten finden. Verwenden Sie beim Speichern von Anwendungseinstellungen anstelle der Registrierung den isolierten Speicher. Der isolierte Speicher kann auch zum Speichern anderer anwendungsspezifischer Dateien verwendet werden. Ebenso können Sie globale Anwendungsinformationen zum Server oder zur Ursprungssite speichern, da Anwendungen standardmäßig berechtigt sind, auf die Ursprungssite zuzugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Mehr Sicherheit beim Drucken in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 [Weitere Überlegungen zur Sicherheit in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [Übersicht über die Sicherheit in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Sicherheit in Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)  
 [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 [MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
