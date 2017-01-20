---
title: "How to: Download a File in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "downloading Internet resources, files"
  - "downloading files"
  - "remote computers, downloading from"
  - "files, downloading"
  - "files, transferring"
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Download a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit der <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>\-Methode kann eine Remotedatei heruntergeladen und an einem bestimmten Speicherort gespeichert werden.  Wenn der `ShowUI`\-Parameter auf `True` festgelegt ist, wird ein Dialogfeld mit dem Fortschritt des Downloads angezeigt. Über dieses Dialogfeld ist auch ein Benutzerabbruch des Vorgangs möglich.  Standardmäßig werden vorhandene Dateien gleichen Namens nicht überschrieben. Wenn vorhandene Dateien überschrieben werden sollen, legen Sie den `overwrite`\-Parameter auf `True` fest.  
  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Laufwerkname ist ungültig \(<xref:System.ArgumentException>\).  
  
-   Es wurden nicht die erforderlichen Authentifizierungsinformationen bereitgestellt \(<xref:System.UnauthorizedAccessException> oder <xref:System.Security.SecurityException>\).  
  
-   Der Server antwortet nicht innerhalb des angegebenen `connectionTimeout` \(<xref:System.TimeoutException>\).  
  
-   Die Anforderung wurde von der Website \(<xref:System.Net.WebException>\) verweigert.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
> [!IMPORTANT]
>  Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.  Bei der Datei Form1.vb handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic\-Quelldatei.  Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.  Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
### So laden Sie eine Datei herunter  
  
-   Verwenden Sie die `DownloadFile`\-Methode zum Herunterladen der Datei, und geben Sie dabei den Speicherort der Ausgangsdatei als Zeichenfolge oder URI sowie den gewünschten Speicherort an.  In diesem Beispiel wird die Datei `WineList.txt` von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` gespeichert:  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### So laden Sie eine Datei unter Angabe eines Timeoutintervalls herunter  
  
-   Verwenden Sie die `DownloadFile`\-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Ausgangsdatei als Zeichenfolge oder URI, den gewünschten Speicherort und das Timeoutintervall in Millisekunden an \(der Standardwert ist 1000\).  In diesem Beispiel wird die Datei `WineList.txt` von `http://www.cohowinery.com/downloads` heruntergeladen und im Verzeichnis `C:\Documents and Settings\All Users\Documents` gespeichert, wobei ein Timeoutintervall von 500 Millisekunden angegeben wird:  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### So laden Sie eine Datei unter Angabe eines Benutzernamens und eines Kennworts herunter  
  
-   Verwenden Sie die `DownLoadFile`\-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Ausgangsdatei als Zeichenfolge oder URI, den gewünschten Speicherort, den Benutzernamen und das Kennwort an.  In diesem Beispiel wird die Datei `WineList.txt` von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` gespeichert, wobei der Benutzername `anonymous` und ein leeres Kennwort angegeben werden.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  Mit dem von der `DownLoadFile`\-Methode verwendeten FTP\-Protokoll werden Informationen, einschließlich Kennwörter, als Klartext gesendet. Es sollte daher nicht für die Übertragung vertraulicher Informationen verwendet werden.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [How to: Upload a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [Gewusst wie: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)