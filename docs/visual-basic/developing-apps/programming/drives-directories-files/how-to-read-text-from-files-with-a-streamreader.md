---
title: 'Vorgehensweise: Lesen von Text aus Dateien mit einer StreamReader-Klasse (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 829b515a6f99799e26da40aa8ee4ed41130dbc20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660059"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>Vorgehensweise: Lesen von Text aus Dateien mit einer StreamReader-Klasse (Visual Basic)
Das `My.Computer.FileSystem`-Objekt bietet Methoden, mit denen Sie ein <xref:System.IO.TextReader>- und ein <xref:System.IO.TextWriter>-Objekt öffnen können. Diese Methoden, `OpenTextFileWriter` und `OpenTextFileReader`, sind fortgeschrittene Methoden, die nicht in IntelliSense angezeigt werden, es sei denn, Sie wählen die Registerkarte **Alle** aus.  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>Lesen einer Zeile aus einer Datei mit einem Textreader  
  
-   Verwenden Sie die `OpenTextFileReader`-Methode, um das <xref:System.IO.TextReader>-Objekt zu öffnen. und geben Sie die Datei an. In diesem Beispiel wird die Datei `testfile.txt` geöffnet, eine Zeile daraus gelesen und in einem Meldungsfenster angezeigt.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Datei, die gelesen wird, muss eine Textdatei sein.  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.  
  
 Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden. Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die Assembly benötigt zum Lesen aus dieser Datei eine von der <xref:System.Security.Permissions.FileIOPermission>-Klasse gewährte Berechtigungsebene. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../framework/misc/code-access-security-basics.md). Außerdem benötigt der Benutzer Zugriff auf die Datei. Weitere Informationen finden Sie unter [Übersicht über die ACL-Technologie](https://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [SaveFileDialog-Komponente](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
