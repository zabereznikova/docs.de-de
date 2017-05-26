---
title: 'Vorgehensweise: Downloaden einer Datei in Visual Basic | Microsoft-Dokumentation'
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
- downloading Internet resources, files
- downloading files
- remote computers, downloading from
- files, downloading
- files, transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bd37b52d12876dad6ec4b2a1bb34f4987f933c08
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-download-a-file-in-visual-basic"></a>Gewusst wie: Downloaden einer Datei in Visual Basic
Die <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>-Methode kann zum Herunterladen einer Remotedatei verwendet werden und um diese an einem bestimmten Speicherort zu speichern. Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Downloads anzeigt und Benutzern erlaubt, den Vorgang abzubrechen. Standardmäßig werden vorhandene Dateien mit demselben Namen nicht überschrieben. Wenn vorhandene Dateien überschrieben werden sollen, legen Sie den `overwrite`-Parameter auf `True` fest.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Laufwerksname ist ungültig (<xref:System.ArgumentException>).  
  
-   Die erforderliche Authentifizierung wurde nicht bereitgestellt (<xref:System.UnauthorizedAccessException> oder <xref:System.Security.SecurityException>).  
  
-   Der Server antwortet nicht innerhalb der angegebenen `connectionTimeout` (<xref:System.TimeoutException>).  
  
-   Die Anforderung wird von der Website verweigert (<xref:System.Net.WebException>).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
> [!IMPORTANT]
>  Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei. Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden. Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
### <a name="to-download-a-file"></a>So laden Sie eine Datei herunter  
  
-   Verwenden Sie die `DownloadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll. Dieses Beispiel lädt die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` herunter und speichert sie unter `C:\Documents and Settings\All Users\Documents`:  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### <a name="to-download-a-file-specifying-a-time-out-interval"></a>So laden Sie eine Datei herunter und geben ein Timeoutintervall an  
  
-   Verwenden Sie die `DownloadFile`-Methode, um die Datei herunterzuladen. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an sowie den Speicherort, an dem die Datei gespeichert werden soll. Geben Sie ebenso das Timeoutintervall in Millisekunden an (der Standardwert ist 1000). In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` gespeichert, wobei ein Timeoutintervall von 500 Millisekunden angegeben ist:  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts herunter  
  
-   Verwenden Sie die `DownLoadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll, sowie den Benutzernamen und das Kennwort. In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` mit dem Benutzernamen `anonymous` und einem leeren Kennwort gespeichert.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  Das FTP-Protokoll, das von der `DownLoadFile`-Methode verwendet wird, sendet Informationen in Klartext, einschließlich Kennwörter, und darf nicht für die Übermittlung vertraulicher Informationen verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [Vorgehensweise: Hochladen einer Datei](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [Gewusst wie: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

