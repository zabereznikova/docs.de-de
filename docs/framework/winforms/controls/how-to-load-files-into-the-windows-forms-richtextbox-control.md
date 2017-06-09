---
title: "Gewusst wie: Laden von Dateien in das RichTextBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
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
  - "Textfelder, Anzeigen von Dateien"
  - "Beispiele [Windows Forms], Textfelder"
  - "RTF-Dateien, Öffnen im RichTextBox-Steuerelement"
  - "RTF-Dateien, Öffnen im RichTextBox-Steuerelement"
  - "Textdateien, Anzeigen in RichTextBox-Steuerelement"
  - "RTF-Dateien, Anzeigen in RichTextBox-Steuerelementen"
  - "RichTextBox-Steuerelement [Windows Forms], Öffnen von Dateien"
  - "RTF-Dateien, Anzeigen in RichTextBox-Steuerelement"
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Laden von Dateien in das RichTextBox-Steuerelement von Windows&#160;Forms
Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement von Windows Forms kann eine Nur\-Text\-, Unicode\-Nur\-Text\- oder Rich\-Text\-Format\-Datei \(RTF\) anzeigen. Rufen Sie dazu die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A>\-Methode auf. Sie können die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A>\-Methode auch zum Laden von Daten aus einem Stream verwenden. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### So laden Sie eine Datei in das RichTextBox\-Steuerelement  
  
1.  Bestimmen Sie den Pfad der Datei, die geöffnet werden soll, mithilfe der <xref:System.Windows.Forms.OpenFileDialog>\-Komponente. Eine Übersicht finden Sie unter [Übersicht über die OpenFileDialog\-Komponente](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).  
  
2.  Rufen Sie die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A>\-Methode des <xref:System.Windows.Forms.RichTextBox>\-Steuerelements auf und geben Sie dabei die zu ladende Datei und optional einen Dateityp an. Im folgenden Beispiel stammt die zu ladende Datei aus der <xref:System.Windows.Forms.FileDialog.FileName%2A>\-Eigenschaft der <xref:System.Windows.Forms.OpenFileDialog> Komponente. Wenn Sie die Methode mit einem Dateinamen als einziges Argument aufrufen, wird RTF als Dateityp angenommen. Rufen Sie zum Angeben eines anderen Dateityps die Methode mit dem Wert der <xref:System.Windows.Forms.RichTextBoxStreamType>\-Enumeration als zweites Argument auf.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.OpenFileDialog>\-Komponente angezeigt, wenn auf eine Schaltfläche geklickt wird. Die ausgewählte Datei wird anschließend geöffnet und im <xref:System.Windows.Forms.RichTextBox>\-Steuerelement angezeigt. In diesem Beispiel wird angenommen, dass eine Form eine Schaltfläche `btnOpenFile` enthält.  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code in den Konstruktor der Form ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  Die Assembly benötigt zum Ausführen dieses Prozesses möglicherweise eine von der <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>\-Klasse gewährte Berechtigungsebene. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)