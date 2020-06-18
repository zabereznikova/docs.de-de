---
title: 'Vorgehensweise: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 02/11/2019
description: Erfahren Sie, wie Sie die OpenFileDialog-Komponente verwenden, um das Dialogfeld Windows zum Durchsuchen und Auswählen von Dateien zu öffnen.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d571885011b0f0c723c73a417f294f30f96952f4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904428"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Gewusst wie: Öffnen von Dateien mit OpenFileDialog

Die <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> -Komponente öffnet das Dialogfeld Windows zum Durchsuchen und Auswählen von Dateien. Sie können die- <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> Methode verwenden oder eine Instanz der-Klasse erstellen, um die ausgewählten Dateien zu öffnen und zu lesen <xref:System.IO.StreamReader?displayProperty=nameWithType> . In den folgenden Beispielen werden beide Vorgehensweisen veranschaulicht.

In .NET Framework ist für die- <xref:System.Windows.Forms.FileDialog.FileName%2A> Eigenschaft eine Berechtigungsebene erforderlich, die von der-Klasse erteilt wurde <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> . In den Beispielen <xref:System.Security.Permissions.FileIOPermission> wird eine Berechtigungsüberprüfung ausgeführt, und es kann eine Ausnahme aufgrund unzureichender Berechtigungen ausgelöst werden, wenn Sie in einem teilweise vertrauenswürdigen Kontext ausgeführt werden. Weitere Informationen finden Sie unter [Grundlagen der Code Zugriffssicherheit](../../misc/code-access-security-basics.md).

Sie können diese Beispiele als .NET Framework-Apps über die c#-oder Visual Basic-Befehlszeile erstellen und ausführen. Weitere Informationen finden Sie unter Erstellen [über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Build über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

Ab .net Core 3,0 können Sie die Beispiele auch als Windows .net Core-Apps aus einem Ordner erstellen und ausführen, der über eine .net Core Windows Forms * \<folder name> . csproj* -Projektdatei verfügt.

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Beispiel: Lesen einer Datei als Stream mit StreamReader  
  
Im folgenden Beispiel wird der <xref:System.Windows.Forms.Button> -Ereignishandler des Windows Forms-Steuer Elements verwendet <xref:System.Windows.Forms.Control.Click> , um <xref:System.Windows.Forms.OpenFileDialog> mit der-Methode zu öffnen <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> . Nachdem der Benutzer eine Datei ausgewählt und **OK**ausgewählt hat, liest eine Instanz der <xref:System.IO.StreamReader> -Klasse die Datei und zeigt ihren Inhalt im Textfeld des Formulars an. Weitere Informationen zum Lesen aus Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> und <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Beispiel: Öffnen einer Datei aus einer gefilterten Auswahl mit OpenFile

Im folgenden Beispiel wird der <xref:System.Windows.Forms.Button> -Ereignishandler des-Steuer Elements verwendet <xref:System.Windows.Forms.Control.Click> , um den <xref:System.Windows.Forms.OpenFileDialog> mit einem Filter zu öffnen, der nur Textdateien anzeigt. Nachdem der Benutzer eine Textdatei ausgewählt und **OK**ausgewählt hat, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> wird die-Methode verwendet, um die Datei im Editor zu öffnen.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog-Komponente](openfiledialog-component-windows-forms.md)
