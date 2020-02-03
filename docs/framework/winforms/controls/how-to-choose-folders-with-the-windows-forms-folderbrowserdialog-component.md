---
title: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente
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
ms.openlocfilehash: 313388442101f341cfed366143f3c9669fb45cbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742231"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms

Häufig müssen Sie in von Ihnen erstellten Windows-Anwendungen Benutzer auffordern, einen Ordner auszuwählen, meistens zum Speichern einer Gruppe von Dateien. Mit der Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog>-Komponente können Sie diese Aufgabe problemlos erledigen.

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>So wählen Sie Ordner mit der FolderBrowserDialog-Komponente

1. Aktivieren Sie in einer Prozedur die <xref:System.Windows.Forms.Form.DialogResult%2A>-Eigenschaft der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente, um zu sehen, wie das Dialogfeld geschlossen wurde, und den Wert der <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>-Eigenschaft der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente zu erhalten.

2. Wenn Sie den obersten Ordner festlegen müssen, der in der Strukturansicht des Dialog Felds angezeigt wird, legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>-Eigenschaft fest, die ein Member der <xref:System.Environment.SpecialFolder>-Enumeration annimmt.

3. Außerdem können Sie die <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>-Eigenschaft festlegen, die die Text Zeichenfolge angibt, die am oberen Rand der Ordner-Browser Strukturansicht angezeigt wird.

    Im folgenden Beispiel wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente verwendet, um einen Ordner auszuwählen, ähnlich dem, wenn Sie ein Projekt in Visual Studio erstellen und zum Auswählen eines Ordners aufgefordert werden, in dem Sie gespeichert werden sollen. In diesem Beispiel wird der Ordnername in einem <xref:System.Windows.Forms.TextBox>-Steuerelement auf dem Formular angezeigt. Es empfiehlt sich, den Speicherort in einen bearbeitbaren Bereich zu versetzen, wie z. b. ein <xref:System.Windows.Forms.TextBox> Steuerelement, damit Benutzer die Auswahl im Falle von Fehlern oder anderen Problemen bearbeiten können. In diesem Beispiel wird davon ausgegangen, dass ein Formular mit einer <xref:System.Windows.Forms.FolderBrowserDialog> Komponente und einem <xref:System.Windows.Forms.TextBox> Steuerelement.

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
    > Um diese Klasse verwenden zu können, benötigt die Assembly eine Berechtigungsebene, die von der <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>-Eigenschaft gewährt wird, die Teil der <xref:System.Security.Permissions.FileIOPermissionAccess>-Enumeration ist. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Code Access Security Basics](../../misc/code-access-security-basics.md).

Informationen zum Speichern von Dateien finden Sie unter [Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente](how-to-save-files-using-the-savefiledialog-component.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [FolderBrowserDialog-Komponente](folderbrowserdialog-component-windows-forms.md)
