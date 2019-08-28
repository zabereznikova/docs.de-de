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
ms.openlocfilehash: fc19ea466f535f783d3b0537a973ce41c223902d
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046134"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Vorgehensweise: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms

Häufig müssen Sie in von Ihnen erstellten Windows-Anwendungen Benutzer auffordern, einen Ordner auszuwählen, meistens zum Speichern einer Gruppe von Dateien. Mit der <xref:System.Windows.Forms.FolderBrowserDialog> Windows Forms-Komponente können Sie diese Aufgabe problemlos ausführen.

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>So wählen Sie Ordner mit der FolderBrowserDialog-Komponente

1. Überprüfen Sie in einer- <xref:System.Windows.Forms.FolderBrowserDialog> Prozedur die <xref:System.Windows.Forms.Form.DialogResult%2A> -Eigenschaft der Komponente, um zu sehen, wie das Dialogfeld geschlossen wurde <xref:System.Windows.Forms.FolderBrowserDialog> , und <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> erhalten Sie den Wert der-Eigenschaft der Komponente.

2. Wenn Sie den obersten Ordner festlegen müssen, der in der Strukturansicht des Dialog Felds angezeigt wird, legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft fest, die ein Member <xref:System.Environment.SpecialFolder> der-Enumeration annimmt.

3. Darüber hinaus können Sie die <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> -Eigenschaft festlegen, die die Text Zeichenfolge angibt, die am oberen Rand der Ordner-Browser Strukturansicht angezeigt wird.

    Im folgenden Beispiel wird die <xref:System.Windows.Forms.FolderBrowserDialog> -Komponente verwendet, um einen Ordner auszuwählen, ähnlich dem, wenn Sie ein Projekt in Visual Studio erstellen und zum Auswählen eines Ordners aufgefordert werden, in dem Sie gespeichert werden sollen. In diesem Beispiel wird der Ordnername in einem <xref:System.Windows.Forms.TextBox> -Steuerelement auf dem Formular angezeigt. Es empfiehlt sich, die Position in einem bearbeitbaren Bereich, z. b. einem <xref:System.Windows.Forms.TextBox> Steuerelement, zu platzieren, damit Benutzer Ihre Auswahl im Falle von Fehlern oder anderen Problemen bearbeiten können. In diesem Beispiel wird ein Formular mit <xref:System.Windows.Forms.FolderBrowserDialog> einer-Komponente <xref:System.Windows.Forms.TextBox> und einem-Steuerelement angenommen.

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
    > Um diese Klasse verwenden zu können, benötigt die Assembly eine Berechtigungsebene <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> , die von der-Eigenschaft gewährt <xref:System.Security.Permissions.FileIOPermissionAccess> wird, die Teil der-Enumeration ist. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).

Informationen zum Speichern von Dateien finden [Sie unter Gewusst wie: Speichern Sie Dateien mithilfe der SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md)-Komponente.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [FolderBrowserDialog-Komponente](folderbrowserdialog-component-windows-forms.md)
