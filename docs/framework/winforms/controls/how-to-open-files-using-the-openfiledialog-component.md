---
title: 'Gewusst wie: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182131"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Gewusst wie: Öffnen von Dateien mit dem OpenFileDialog

Die <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> Komponente öffnet das Windows-Dialogfeld zum Durchsuchen und Auswählen von Dateien. Um die ausgewählten Dateien zu öffnen <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> und zu lesen, können <xref:System.IO.StreamReader?displayProperty=nameWithType> Sie die Methode verwenden oder eine Instanz der Klasse erstellen. Die folgenden Beispiele zeigen beide Ansätze.

In .NET Framework erfordert das <xref:System.Windows.Forms.FileDialog.FileName%2A> Abrufen oder Festlegen der <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Eigenschaft eine von der Klasse gewährte Berechtigungsstufe. Die Beispiele <xref:System.Security.Permissions.FileIOPermission> führen eine Berechtigungsprüfung aus und können eine Ausnahme aufgrund unzureichender Berechtigungen auslösen, wenn sie in einem Kontext mit teilweiser Vertrauenswürdigkeit ausgeführt werden. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).

Sie können diese Beispiele als .NET Framework-Apps über die Befehlszeile "C" oder "Visual Basic" erstellen und ausführen. Weitere Informationen finden Sie unter [Befehlszeilenerstellung mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Build über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

Ab .NET Core 3.0 können Sie die Beispiele auch als Windows .NET Core-Apps aus einem Ordner mit dem Ordnernamen .NET Core Windows Forms * \<>.csproj-Projektdatei* erstellen und ausführen.

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Beispiel: Lesen einer Datei als Stream mit StreamReader  
  
Im folgenden Beispiel wird <xref:System.Windows.Forms.Button> der <xref:System.Windows.Forms.Control.Click> Ereignishandler des <xref:System.Windows.Forms.OpenFileDialog> Windows <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Forms-Steuerelements verwendet, um den mit der Methode zu öffnen. Nachdem der Benutzer eine Datei ausgewählt und **OK** <xref:System.IO.StreamReader> ausgewählt hat, liest eine Instanz der Klasse die Datei und zeigt deren Inhalt im Textfeld des Formulars an. Weitere Informationen zum Lesen aus <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> Dateistreams finden Sie unter und <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Beispiel: Öffnen einer Datei aus einer gefilterten Auswahl mit OpenFile

Im folgenden Beispiel <xref:System.Windows.Forms.Button> wird <xref:System.Windows.Forms.Control.Click> der Ereignishandler <xref:System.Windows.Forms.OpenFileDialog> des Steuerelements verwendet, um den mit einem Filter zu öffnen, der nur Textdateien anzeigt. Nachdem der Benutzer eine Textdatei **OK**ausgewählt und <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> OK ausgewählt hat, wird die Methode zum Öffnen der Datei in Notepad verwendet.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog-Komponente](openfiledialog-component-windows-forms.md)
