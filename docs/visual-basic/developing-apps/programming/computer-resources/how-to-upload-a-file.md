---
title: "How to: Upload a File in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "networks, uploading files"
  - "files, uploading"
  - "uploading files"
  - "UploadFile method"
  - "My.Computer.Network.UploadFile method"
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# How to: Upload a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit der <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>\-Methode kann eine Datei hochgeladen und an einem Remotespeicherort gespeichert werden.  Wenn der `ShowUI`\-Parameter auf `True` festgelegt ist, wird ein Dialogfeld mit dem Fortschritt des Downloads angezeigt. Über dieses Dialogfeld ist auch ein Benutzerabbruch des Vorgangs möglich.  
  
### So laden Sie eine Datei hoch  
  
-   Verwenden Sie die `UploadFile`\-Methode zum Hochladen einer Datei. Geben Sie dabei den Speicherort der Quelldatei sowie das Zielverzeichnis als Zeichenfolge oder URI \(Uniform Resource Identifier\) an. In diesem Beispiel wird die Datei `Order.txt` auf `http://www.cohowinery.com/uploads.aspx` hochgeladen.  
  
     [!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-upload-a-file_1.vb)]  
  
### So laden Sie eine Datei hoch und zeigen den Fortschritt der Operation an  
  
-   Verwenden Sie die `UploadFile`\-Methode zum Hochladen einer Datei, und geben Sie dabei den Speicherort der Quelldatei und das Zielverzeichnis als Zeichenfolge oder URI an.  In diesem Beispiel wird die Datei `Order.txt` auf `http://www.cohowinery.com/uploads.aspx` hochgeladen, ohne einen Benutzernamen oder ein Kennwort anzugeben. Der Status des Uploads wird angezeigt, und das Timeoutintervall beträgt 500 Millisekunden.  
  
     [!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-upload-a-file_2.vb)]  
  
### So laden Sie eine Datei unter Angabe eines Benutzernamens und eines Kennworts hoch  
  
-   Verwenden Sie die `UploadFile`\-Methode zum Hochladen einer Datei. Geben Sie dabei den Speicherort der Quelldatei und das Zielverzeichnis als Zeichenfolge oder URI sowie den Benutzernamen und das Kennwort an.  In diesem Beispiel wird die Datei `Order.txt` unter Angabe des Benutzernamens `anonymous` und eines leeren Kennworts auf `http://www.cohowinery.com/uploads.aspx` hochgeladen.  
  
     [!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-upload-a-file_3.vb)]  
  
## Robuste Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad der lokalen Datei ist nicht gültig \(<xref:System.ArgumentException>\).  
  
-   Die Authentifizierung ist fehlgeschlagen \(<xref:System.Security.SecurityException>\).  
  
-   Timeout der Verbindung \(<xref:System.TimeoutException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>   
 [How to: Download a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)   
 [Gewusst wie: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)