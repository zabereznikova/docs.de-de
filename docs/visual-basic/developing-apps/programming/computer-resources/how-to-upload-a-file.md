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
ms.openlocfilehash: 486351bc140a2bbf18bb8f85f761fc491f028bba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840353"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a>Vorgehensweise: Hochladen einer Datei in Visual Basic
Die <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>-Methode kann zum Hochladen einer Datei und zum Speichern derselben an einem Remotespeicherort verwendet werden. Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Hochladens anzeigt und Benutzern erlaubt, den Vorgang abzubrechen.  
  
### <a name="to-upload-a-file"></a>Hochladen einer Datei  
  
-   Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI (Uniform Resource Identifier) an. In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen.  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a>Hochladen einer Datei und Anzeigen des Fortschritts des Vorgangs  
  
-   Verwenden Sie die `UploadFile`-Methode, um eine Datei hochzuladen, und geben Sie den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an. In diesem Beispiel wird `Order.txt` ohne Benutzername und Kennwort in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Hochladeprozess wird gezeigt. Das Timeoutintervall beträgt 500 Millisekunden.  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a>So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts hoch  
  
-   Verwenden Sie die `UploadFile`-Methode zum Hochladen der Datei. Geben Sie dabei den Speicherort der Quelldatei und des Zielverzeichnisses als Zeichenfolge oder URI an, und geben Sie den Benutzernamen und das Kennwort an. In diesem Beispiel wird die Datei `Order.txt` in `http://www.cohowinery.com/uploads.aspx` hochgeladen. Der Benutzername `anonymous` und ein leeres Kennwort werden bereitgestellt.  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
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
