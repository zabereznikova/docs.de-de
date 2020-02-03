---
title: Speichern von Dateien mit dem RichTextBox-Steuerelement
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
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744818"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Gewusst wie: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows Forms

Das Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement kann die angezeigten Informationen in einem von mehreren Formaten schreiben:

- Nur-Text

- Unicode-nur-Text

- Rich-Text-Format (RTF)

- RTF mit Leerzeichen anstelle von OLE-Objekten

- Klartext mit Textdarstellung von OLE-Objekten

Um eine Datei zu speichern, nennen Sie die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>-Methode. Sie können auch die **SaveFile** -Methode verwenden, um Daten in einem Stream zu speichern. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.

### <a name="to-save-the-contents-of-the-control-to-a-file"></a>So speichern Sie den Inhalt des Steuer Elements in einer Datei

1. Bestimmen Sie den Pfad der zu speichernden Datei.

    Um dies in einer realen Anwendung zu erreichen, verwenden Sie in der Regel die <xref:System.Windows.Forms.SaveFileDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die SaveFileDialog-Komponente](savefiledialog-component-overview-windows-forms.md).

2. Ruft die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>-Methode des <xref:System.Windows.Forms.RichTextBox> Steuer Elements auf und gibt die zu speichernde Datei und optional einen Dateityp an. Wenn Sie die Methode mit einem Dateinamen als einziges Argument aufzurufen, wird die Datei als RTF gespeichert. Rufen Sie zum Angeben eines anderen Dateityps die Methode mit dem Wert der <xref:System.Windows.Forms.RichTextBoxStreamType> -Enumeration als zweites Argument auf.

    Im folgenden Beispiel ist der Pfad, der für den Speicherort der Rich-Text-Datei festgelegt ist, der Ordner " **eigene** Dateien". Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer unter dem Windows-Betriebssystem diesen Ordner enthalten. Wenn Sie diesen Speicherort auswählen, können Benutzer mit minimalen System Zugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird davon ausgegangen, dass ein <xref:System.Windows.Forms.RichTextBox> Formular bereits hinzugefügt wurde.

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
    > Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist. Wenn eine Anwendung eine Datei erstellen muss, muss diese Anwendung Zugriff auf den Ordner erstellen. Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung nur Schreibzugriff, eine geringere Berechtigung. Wenn möglich, ist es sicherer, die Datei während der Bereitstellung zu erstellen, und nur Lesezugriff auf eine einzelne Datei zu gewähren, anstatt den Zugriff für einen Ordner zu erstellen. Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programme“ zu schreiben.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
