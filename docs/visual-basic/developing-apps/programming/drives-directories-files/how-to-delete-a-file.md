---
title: "Vorgehensweise: Löschen einer Datei in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Delete method
- files, deleting
- files, manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f6cf3192d6983b6222815c5c77a3dfd0b3845650
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-delete-a-file-in-visual-basic"></a>Gewusst wie: Löschen einer Datei in Visual Basic
Die `DeleteFile`-Methode des `My.Computer.FileSystem`-Objekts ermöglicht das Löschen einer Textdatei. Sie bietet u.a. folgende Optionen: ob die gelöschte Datei in den **Papierkorb** verschoben werden soll, ob der Benutzer den Löschvorgang bestätigen muss und was passiert, wenn der Benutzer den Vorgang abbricht.  
  
### <a name="to-delete-a-text-file"></a>Löschen einer Textdatei  
  
-   Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei. Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können.  
  
     [!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a>Löschen einer Textdatei und Bestätigen des Löschvorgangs der Datei durch den Benutzer  
  
-   Verwenden Sie die `DeleteFile`-Methode zum Löschen der Datei, und legen Sie `showUI` auf `AllDialogs` fest. Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen können, und wie Sie dem Benutzer das Bestätigen des Löschvorgangs ermöglichen.  
  
     [!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a>Löschen einer Textdatei und anschließendes Verschieben in den Papierkorb  
  
-   Verwenden Sie die `DeleteFile`-Methode, um die Datei zu löschen, und geben Sie `SendToRecycleBin` für den `recycle`-Parameter an. Der folgende Code veranschaulicht, wie Sie die Datei mit dem Namen `test.txt` löschen und sie in den **Papierkorb** verschieben können.  
  
     [!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0 (null), er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Der Pfad ist ungültig, da er `Nothing` entspricht (<xref:System.ArgumentNullException>).  
  
-   Der Pfad überschreitet die vom System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
-   Ein Datei- oder Ordnername im Pfad enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
-   Die Datei wird gerade verwendet (<xref:System.IO.IOException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
-   Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
-   Der Benutzer verfügt nicht über die nötigen Berechtigungen, um die Datei zu löschen, oder die Datei ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).  
  
-   Es gibt eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen verfügt (<xref:System.Security.SecurityException>).  
  
-   Der Benutzer hat den Vorgang abgebrochen, und `onUserCancel` wird auf `ThrowException` festgelegt (<xref:System.OperationCanceledException>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.UIOption>   
 <xref:Microsoft.VisualBasic.FileIO.RecycleOption>   
 [Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
