---
title: 'Vorgehensweise: Hochladen einer Datei in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: 0d0aaca06a72b9bd2631a652a0b4756f4681df7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704406"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a>Vorgehensweise: Hochladen einer Datei in Visual Basic
Die <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>-Methode kann zum Hochladen einer Datei und zum Speichern derselben an einem Remotespeicherort verwendet werden. Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Hochladens anzeigt und Benutzern erlaubt, den Vorgang abzubrechen.  
  
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
  
-   Der Dateipfad ist ungültig (<xref:System.ArgumentException>).  
  
-   Die Authentifizierung ist fehlgeschlagen (<xref:System.Security.SecurityException>).  
  
-   Verbindungstimeout (<xref:System.TimeoutException>)  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [Vorgehensweise: Herunterladen einer Datei](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)
- [Vorgehensweise: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
