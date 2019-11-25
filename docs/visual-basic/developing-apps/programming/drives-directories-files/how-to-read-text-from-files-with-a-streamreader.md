---
title: 'Vorgehensweise: Lesen von Text aus Dateien mit StreamReader'
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 572463d1f03d768fb133f2dac59b012051f053bb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74334564"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>Vorgehensweise: Lesen von Text aus Dateien mit einer StreamReader-Klasse (Visual Basic)

Das `My.Computer.FileSystem`-Objekt bietet Methoden, mit denen Sie ein <xref:System.IO.TextReader>- und ein <xref:System.IO.TextWriter>-Objekt öffnen können. Diese Methoden, `OpenTextFileWriter` und `OpenTextFileReader`, sind fortgeschrittene Methoden, die nicht in IntelliSense angezeigt werden, es sei denn, Sie wählen die Registerkarte **Alle** aus.  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>Lesen einer Zeile aus einer Datei mit einem Textreader  
  
- Verwenden Sie die `OpenTextFileReader`-Methode, um das <xref:System.IO.TextReader>-Objekt zu öffnen. und geben Sie die Datei an. In diesem Beispiel wird die Datei `testfile.txt` geöffnet, eine Zeile daraus gelesen und in einem Meldungsfenster angezeigt.  
  
     [!code-vb[VbFileIORead#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#1)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die Datei, die gelesen wird, muss eine Textdatei sein.  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.  
  
 Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden. Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Die Assembly benötigt zum Lesen aus dieser Datei eine von der <xref:System.Security.Permissions.FileIOPermission>-Klasse gewährte Berechtigungsebene. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../framework/misc/code-access-security-basics.md). Außerdem benötigt der Benutzer Zugriff auf die Datei. Weitere Informationen finden Sie unter [Übersicht über die ACL-Technologie](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [SaveFileDialog-Komponente](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
