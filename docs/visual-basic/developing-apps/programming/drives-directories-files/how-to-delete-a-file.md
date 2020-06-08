---
title: 'Gewusst wie: Löschen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 0c8213786b8073d784f1f3ea51417741d5ad4cba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401653"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a>Gewusst wie: Löschen einer Datei in Visual Basic

Die `DeleteFile`-Methode des `My.Computer.FileSystem`-Objekts ermöglicht das Löschen einer Textdatei. Sie bietet u.a. folgende Optionen: ob die gelöschte Datei in den **Papierkorb** verschoben werden soll, ob der Benutzer den Löschvorgang bestätigen muss und was passiert, wenn der Benutzer den Vorgang abbricht.  
  
### <a name="to-delete-a-text-file"></a>Löschen einer Textdatei  
  
- Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei. Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können.  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a>Löschen einer Textdatei und Bestätigen des Löschvorgangs der Datei durch den Benutzer  
  
- Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei, und legen Sie `showUI` auf `AllDialogs` fest. Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können, und wie Sie dem Benutzer das Bestätigen des Löschvorgangs ermöglichen.  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a>Löschen einer Textdatei und anschließendes Verschieben in den Papierkorb  
  
- Verwenden Sie die `DeleteFile`-Methode, um die Datei zu löschen, und geben Sie `SendToRecycleBin` für den `recycle`-Parameter an. Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen und sie in den **Papierkorb** verschieben können.  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
- Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
- Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
- Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).  
  
- Die Datei wird gerade verwendet (<xref:System.IO.IOException>).  
  
- Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
- Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
- Der Benutzer verfügt nicht über die nötigen Berechtigungen, um die Datei zu löschen, oder die Datei ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).  
  
- Ein teilweise vertrauenswürdiger Kontext, in dem der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt (<xref:System.Security.SecurityException>).  
  
- Der Benutzer hat den Vorgang abgebrochen, und `onUserCancel` wird auf `ThrowException` festgelegt (<xref:System.OperationCanceledException>).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis](how-to-get-the-collection-of-files-in-a-directory.md)
