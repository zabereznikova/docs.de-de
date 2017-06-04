---
title: "Gewusst wie: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
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
  - ".rtf-Dateien, Speichern im RichTextBox-Steuerelement"
  - "Beispiele [Windows Forms], Textfelder"
  - "Dateien, Speichern mit dem RichTextBox-Steuerelement"
  - "RichTextBox-Steuerelement [Windows Forms], Speichern von Dateien"
  - "RTF-Dateien, Speichern im RichTextBox-Steuerelement"
  - "Speichern von Dateien"
  - "Speichern von Dateien, RichTextBox-Steuerelement"
  - "Textdateien, Speichern eines RichTextBox-Steuerelements"
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows&#160;Forms
Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement von Windows Forms kann die in ihm angezeigten Informationen in verschiedenen Formaten ausgeben:  
  
-   Nur\-Text  
  
-   Unicode\-Nur\-Text  
  
-   Rich Text Format \(RTF\)  
  
-   RTF mit Leerzeichen anstelle von OLE\-Objekten  
  
-   Nur\-Text mit einer Textdarstellung von OLE\-Objekten  
  
 Rufen Sie zum Speichern einer Datei die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>\-Methode auf.  Sie können die **SaveFile**\-Methode auch zum Speichern von Daten in einen Stream verwenden.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### So speichern Sie den Inhalt des Steuerelements in einer Datei  
  
1.  Bestimmen Sie den Pfad der zu speichernden Datei.  
  
     In einer realen Anwendung wird hierzu normalerweise die <xref:System.Windows.Forms.SaveFileDialog>\-Komponente verwendet.  Eine Übersicht finden Sie unter [Übersicht über die SaveFileDialog\-Komponente](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).  
  
2.  Rufen Sie die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>\-Methode des <xref:System.Windows.Forms.RichTextBox>\-Steuerelements auf, und geben Sie die zu speichernde Datei und optional einen Dateityp an.  Wenn Sie die Methode mit einem Dateinamen als einziges Argument aufrufen, wird die Datei im RTF\-Format gespeichert.  Rufen Sie zum Angeben eines anderen Dateityps die Methode mit einem Wert der <xref:System.Windows.Forms.RichTextBoxStreamType>\-Enumeration als zweites Argument auf.  
  
     Im nachstehenden Beispiel wurde als Speicherort der RTF\-Datei der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit Windows als Betriebssystem über einen Ordner mit diesem Namen verfügen.  Dieser Speicherort ermöglicht auch Benutzern mit minimalen Systemzugriffsberechtigungen, die Anwendung sicher auszuführen.  Im unten stehenden Beispiel wird davon ausgegangen, dass einem Formular bereits ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement hinzugefügt wurde.  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.  Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine Erstellungsberechtigung für den Ordner.  Berechtigungen werden unter Verwendung von Zugriffssteuerungslisten festgelegt.  Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den Schreibzugriff, also eine geringere Berechtigung.  Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die Leseberechtigung für eine einzelne Datei erteilt werden \(anstatt Erstellungsberechtigungen für den gesamten Ordner zu gewähren\).  Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in den Stammordner oder den Ordner Programme zu schreiben.  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)