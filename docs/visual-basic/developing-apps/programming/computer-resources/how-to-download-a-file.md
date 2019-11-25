---
title: 'Vorgehensweise: Herunterladen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: 4923feb46ff638de9514a4d70fc00367491a6f44
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345620"
---
# <a name="how-to-download-a-file-in-visual-basic"></a>Vorgehensweise: Herunterladen einer Datei in Visual Basic

Die <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>-Methode kann zum Herunterladen einer Remotedatei und dazu verwendet werden, diese an einem bestimmten Speicherort zu speichern. Wenn der `ShowUI`-Parameter auf `True` festgelegt wird, wir ein Dialogfeld angezeigt, das den Fortschritt des Downloads anzeigt und Benutzern erlaubt, den Vorgang abzubrechen. Standardmäßig werden vorhandene Dateien mit demselben Namen nicht überschrieben. Wenn vorhandene Dateien überschrieben werden sollen, legen Sie den `overwrite`-Parameter auf `True` fest.

Die folgenden Bedingungen können einen Ausnahmefehler verursachen:

- Der Laufwerksname ist ungültig (<xref:System.ArgumentException>).

- Die erforderliche Authentifizierung wurde nicht bereitgestellt (<xref:System.UnauthorizedAccessException> oder <xref:System.Security.SecurityException>).

- Der Server antwortet nicht innerhalb der angegebenen `connectionTimeout` (<xref:System.TimeoutException>).

- Die Anforderung wird von der Website verweigert (<xref:System.Net.WebException>).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

> [!IMPORTANT]
> Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei. Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden. Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.

### <a name="to-download-a-file"></a>So laden Sie eine Datei herunter

- Verwenden Sie die `DownloadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll. Dieses Beispiel lädt die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` herunter und speichert sie unter `C:\Documents and Settings\All Users\Documents`:

  [!code-vb[VbResourceTasks#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#9)]

### <a name="to-download-a-file-specifying-a-time-out-interval"></a>So laden Sie eine Datei herunter und geben ein Timeoutintervall an

- Verwenden Sie die `DownloadFile`-Methode, um die Datei herunterzuladen. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an sowie den Speicherort, an dem die Datei gespeichert werden soll. Geben Sie ebenso das Timeoutintervall in Millisekunden an (der Standardwert ist 1000). In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` gespeichert, wobei ein Timeoutintervall von 500 Millisekunden angegeben ist:

  [!code-vb[VbResourceTasks#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#10)]

### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>So laden Sie eine Datei unter Angabe eines Benutzernamens und Kennworts herunter

- Verwenden Sie die `DownLoadFile`-Methode zum Herunterladen der Datei. Geben Sie dabei den Speicherort der Zieldatei als Zeichenfolge oder URI an, und geben Sie den Speicherort an, an dem die Datei gespeichert werden soll, sowie den Benutzernamen und das Kennwort. In diesem Beispiel wird die `WineList.txt`-Datei von `http://www.cohowinery.com/downloads` heruntergeladen und unter `C:\Documents and Settings\All Users\Documents` mit dem Benutzernamen `anonymous` und einem leeren Kennwort gespeichert.

  [!code-vb[VbResourceTasks#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#11)]

  > [!IMPORTANT]
  > Das FTP-Protokoll, das von der `DownLoadFile`-Methode verwendet wird, sendet Informationen in Klartext, einschließlich Kennwörter, und darf nicht für die Übermittlung vertraulicher Informationen verwendet werden.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>
- [Vorgehensweise: Hochladen einer Datei](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)
- [Vorgehensweise: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
