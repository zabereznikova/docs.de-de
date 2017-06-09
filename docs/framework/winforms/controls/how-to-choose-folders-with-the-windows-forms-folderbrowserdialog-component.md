---
title: "Gewusst wie: Ausw&#228;hlen von Ordnern mit der FolderBrowserDialog-Komponente in Windows&#160;Forms | Microsoft Docs"
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
  - "Verzeichnisse [Windows Forms], Auswählen"
  - "Verzeichnisse [Windows Forms], Auswählen"
  - "FolderBrowserDialog-Komponente [Windows Forms], Auswählen von Verzeichnissen"
  - "Ordner [Windows Forms], Auswählen"
  - "Ordner [Windows Forms], Auswählen"
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Ausw&#228;hlen von Ordnern mit der FolderBrowserDialog-Komponente in Windows&#160;Forms
Häufig müssen Sie in von Ihnen erstellten Windows\-Anwendungen Benutzer auffordern, einen Ordner auszuwählen – meistens zum Speichern einer Gruppe von Dateien.  Mit der <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente in Windows Forms können Sie diese Aufgabenstellung problemlos umsetzen.  
  
### So wählen Sie Ordner mit der FolderBrowserDialog\-Komponente  
  
1.  Prüfen Sie in einer Prozedur die <xref:System.Windows.Forms.Form.DialogResult%2A>\-Eigenschaft der <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente, um festzustellen, wie das Dialogfeld geschlossen wurde, und ermitteln Sie den Wert der <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>\-Eigenschaft der <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente.  
  
2.  Wenn Sie den obersten Ordner festlegen müssen, der in der Strukturansicht des Dialogfelds angezeigt wird, legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>\-Eigenschaft fest, die einen Member der [SpecialFolder](frlrfSystemEnvironmentSpecialFolderClassTopic)\-Enumeration verwendet.  
  
3.  Ferner können Sie die <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>\-Eigenschaft festlegen, die angibt, welche Textzeichenfolge an oberster Stelle der Ordnerstrukturansicht angezeigt wird.  
  
     Im nachfolgenden Beispiel wird die <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente zum Auswählen eines Ordners verwendet. Ein vergleichbarer Vorgang findet statt, wenn Sie in Visual Studio ein Projekt erstellen und aufgefordert werden, einen Ordner zum Speichern auszuwählen.  In diesem Beispiel wird der Ordnername anschließend in einem <xref:System.Windows.Forms.TextBox>\-Steuerelement im Formular angezeigt.  Diese Stelle sollte sich in einem bearbeitbaren Bereich befinden \(z. B. einem <xref:System.Windows.Forms.TextBox>\-Steuerelement\), damit Benutzer eine fehlerhafte Eingabe korrigieren können.  Bei diesem Beispiel wird vorausgesetzt, dass ein Formular bereits über eine <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente und ein <xref:System.Windows.Forms.TextBox>\-Steuerelement verfügt.  
  
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
    >  Zur Verwendung dieser Klasse muss die Assembly über eine von der [FileIOPermissionAttribute.PathDiscoveryProperty](frlrfSystemSecurityPermissionsFileIOPermissionAttributeClassPathDiscoveryTopic)\-Eigenschaft gewährte Berechtigungsebene verfügen. Die Eigenschaft ist Teil der <xref:System.Security.Permissions.FileIOPermissionAccess>\-Enumeration.  Bei Ausführung in einer teilweise vertrauenswürdigen Umgebung kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Weitere Informationen finden Sie unter [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
 Informationen zum Speichern von Dateien finden Sie unter [Gewusst wie: Speichern von Dateien mit der SaveFileDialog\-Komponente](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [Übersicht über die FolderBrowserDialog\-Komponente \(Windows Forms\)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)   
 [FolderBrowserDialog\-Komponente](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)