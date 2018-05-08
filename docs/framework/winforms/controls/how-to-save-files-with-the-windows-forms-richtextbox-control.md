---
title: 'Gewusst wie: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: c50b2f3309c1f811b29e824327a709e2cc4bd791
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Gewusst wie: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows Forms
Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement kann Schreiben der Informationen, die in einem von mehreren Formaten angezeigt:  
  
-   Nur-Text  
  
-   Unicode-nur-text  
  
-   Rich-Text-Format (RTF)  
  
-   RTF mit Leerzeichen anstelle von OLE-Objekte  
  
-   Nur-Text mit einer Textdarstellung des OLE-Objekte  
  
 Um eine Datei zu speichern, rufen die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> Methode. Sie können auch die **SaveFile** Methode zum Speichern von Daten in einen Stream. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a>Um den Inhalt des Steuerelements in einer Datei speichern  
  
1.  Bestimmen Sie den Pfad der Datei gespeichert werden soll.  
  
     Zu diesem Zweck in einer realen Anwendung verwenden Sie in der Regel die <xref:System.Windows.Forms.SaveFileDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die SaveFileDialog-Komponente](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).  
  
2.  Rufen Sie die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> Methode der <xref:System.Windows.Forms.RichTextBox> Steuerelement, das die Datei zu speichern und optional einen Dateityp angeben. Wenn Sie die Methode mit einem Dateinamen als einziges Argument aufrufen, wird die Datei im RTF-Format gespeichert. Rufen Sie zum Angeben eines anderen Dateityps die Methode mit dem Wert der <xref:System.Windows.Forms.RichTextBoxStreamType> -Enumeration als zweites Argument auf.  
  
     Im folgenden Beispiel wird der Pfad festgelegt, für der Speicherort der RTF-Datei ist die **eigene** Ordner. Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass dieser Ordner die meisten Computer das Windows-Betriebssystem ausgeführt wird enthält. Dieser Speicherort kann sich Benutzer mit minimalen sicher auf die Anwendung auszuführen. Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement bereits hinzugefügt.  
  
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
    >  Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist. Wenn eine Anwendung eine Datei erstellen muss, benötigt die Anwendung erstellen-Zugriff für den Ordner an. Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung nur Schreibzugriff, also eine geringere Berechtigung. Wenn möglich, ist es sicherer, erstellen Sie die Datei während der Bereitstellung und nur Lesezugriff auf eine einzelne Datei zu gewähren, anstatt den Zugriff für einen Ordner erstellen. Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programme“ zu schreiben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
