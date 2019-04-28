---
title: 'Vorgehensweise: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms'
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
ms.openlocfilehash: 050af6d10faec3dd09998349dcf96e96ea0f9201
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746917"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Vorgehensweise: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms
Häufig müssen Sie in von Ihnen erstellten Windows-Anwendungen Benutzer auffordern, einen Ordner auszuwählen, meistens zum Speichern einer Gruppe von Dateien. Die Windows-Formulare <xref:System.Windows.Forms.FolderBrowserDialog> Komponente können Sie diese Aufgabe problemlos erledigen.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>So wählen Sie Ordner mit der FolderBrowserDialog-Komponente  
  
1. Überprüfen Sie in einer Prozedur die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente <xref:System.Windows.Forms.Form.DialogResult%2A> Eigenschaft, um festzustellen, wie Sie das Dialogfeld geschlossen wurde, und rufen Sie den Wert von der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Eigenschaft.  
  
2. Wenn Sie den obersten Ordner, die in der Strukturansicht des Dialogfelds angezeigt werden müssen, legen die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft, die einen Member verwendet die <xref:System.Environment.SpecialFolder> Enumeration.  
  
3. Darüber hinaus können Sie festlegen der <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> Eigenschaft, die angibt, die Text-Zeichenfolge, wird am oberen Rand der Ordnerbrowser Strukturansicht angezeigt.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente wird verwendet, um Wählen Sie einen Ordner, ähnlich wie wenn Sie ein Projekt in Visual Studio erstellen und werden aufgefordert, einen Ordner zum Speichern auszuwählen. In diesem Beispiel ist der Name des Ordners wird angezeigt einem <xref:System.Windows.Forms.TextBox> Steuerelement im Formular. Es ist eine gute Idee, platzieren den Speicherort in einem bearbeitbaren Bereich, z. B. eine <xref:System.Windows.Forms.TextBox> zu steuern, sodass Benutzer die Auswahl bei einem Fehler oder andere Probleme bearbeiten können. In diesem Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.FolderBrowserDialog> Komponente und eine <xref:System.Windows.Forms.TextBox> Steuerelement.  
  
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
    >  Um diese Klasse verwenden zu können, benötigt Ihre Assembly eine Berechtigungsebene gewährt durch die <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> -Eigenschaft, die Teil von der <xref:System.Security.Permissions.FileIOPermissionAccess> Enumeration. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).  
  
 Weitere Informationen zum Speichern von Dateien, finden Sie unter [Vorgehensweise: Speichern von Dateien mit der SaveFileDialog-Komponente](how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [FolderBrowserDialog-Komponente](folderbrowserdialog-component-windows-forms.md)
