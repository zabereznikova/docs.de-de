---
title: 'Vorgehensweise: Hochladen einer Datei in Visual Basic | Microsoft-Dokumentation'
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
- networks, uploading files
- files, uploading
- uploading files
- UploadFile method
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
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
ms.openlocfilehash: 1663cc6ad0a6e5f2a940c050c75d403cffd1f53f
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-upload-a-file-in-visual-basic"></a>Gewusst wie: Hochladen einer Datei in Visual Basic
Die <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>-Methode kann zum Hochladen einer Datei verwendet werden und um diese an einem bestimmten Remotespeicherort zu speichern. Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Downloads anzeigt und Benutzern erlaubt, den Vorgang abzubrechen.  
  
### <a name="to-upload-a-file"></a>Hochladen einer Datei  
  
-   Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI (Uniform Resource Identifier) an. In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen.  
  
     [!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a>Hochladen einer Datei und Anzeigen des Fortschritts des Vorgangs  
  
-   Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an. In diesem Beispiel wird `Order.txt` ohne Benutzername und Kennwort in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Hochladeprozess wird gezeigt. Das Timeoutintervall beträgt 500 Millisekunden.  
  
     [!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a>So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts hoch  
  
-   Verwenden Sie die `UploadFile`-Methode zum Hochladen der Datei. Geben Sie dabei den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an, und geben Sie den Benutzernamen und das Kennwort an. In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Benutzername `anonymous` und ein leeres Kennwort werden bereitgestellt.  
  
     [!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der lokale Dateipfad ist ungültig (<xref:System.ArgumentException>).  
  
-   Die Authentifizierung ist fehlgeschlagen (<xref:System.Security.SecurityException>).  
  
-   Die Verbindung ist abgelaufen (<xref:System.TimeoutException>).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>   
 [Vorgehensweise: Herunterladen einer Datei](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)   
 [Gewusst wie: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
