---
title: 'Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 657aad6efa195ec3d9741f4f91d4e01af4a54a19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms
Häufig müssen Sie in von Ihnen erstellten Windows-Anwendungen Benutzer auffordern, einen Ordner auszuwählen, meistens zum Speichern einer Gruppe von Dateien. Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> Komponente können Sie einfach diese Aufgabe.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>So wählen Sie Ordner mit der FolderBrowserDialog-Komponente  
  
1.  Überprüfen Sie in einer Prozedur die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente <xref:System.Windows.Forms.Form.DialogResult%2A> angezeigt, wie das Dialogfeld geschlossen wurde, und rufen Sie den Wert der Eigenschaft der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Eigenschaft.  
  
2.  Legen Sie Sie ggf. die oberste Ordner, der in der Strukturansicht des Dialogfelds angezeigt wird, die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft, die ein Mitglied übernimmt die <xref:System.Environment.SpecialFolder> Enumeration.  
  
3.  Darüber hinaus können Sie festlegen der <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> Eigenschaft, die angibt, die Textzeichenfolge, die am oberen Rand der Ordnerbrowser Strukturansicht angezeigt wird.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente verwendet wird, wählen Sie einen Ordner, ähnlich wie beim Erstellen eines Projekts in Visual Studio und werden aufgefordert, speichern ihn in einen Ordner auszuwählen. In diesem Beispiel wird dann der Name des Ordners im angezeigt ein <xref:System.Windows.Forms.TextBox> Steuerelement im Formular. Es ist eine gute Idee, platzieren den Speicherort in einem bearbeitbaren Bereich, z. B. eine <xref:System.Windows.Forms.TextBox> steuern, sodass Benutzer ihre Auswahl bei einem Fehler oder andere Probleme bearbeiten können. In diesem Beispiel wird angenommen, ein Formular mit einem <xref:System.Windows.Forms.FolderBrowserDialog> Komponente und eine <xref:System.Windows.Forms.TextBox> Steuerelement.  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Um diese Klasse verwenden zu können, muss die Assembly eine Berechtigungsebene gewährt durch die <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> -Eigenschaft, die Teil von der <xref:System.Security.Permissions.FileIOPermissionAccess> Enumeration. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).  
  
 Informationen zum Speichern von Dateien finden Sie unter [Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [FolderBrowserDialog-Komponente](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
