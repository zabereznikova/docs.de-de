---
title: 'Gewusst wie: Schreiben von Text in Dateien mit einem StreamWriter'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: 373f3bd07ea61263ddd81037d8cbbb06f789e599
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411576"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a>Gewusst wie: Schreiben von Text in Dateien mit einem StreamWriter in Visual Basic

In diesem Beispiel wird ein <xref:System.IO.StreamWriter>-Objekt mit der `My.Computer.FileSystem.OpenTextFileWriter`-Methode geöffnet. Es wird dazu verwendet, eine Zeichenfolge mit der <xref:System.IO.TextWriter.WriteLine%2A>-Methode der <xref:System.IO.StreamWriter>-Klasse in eine Textdatei zu schreiben.  
  
## <a name="example"></a>Beispiel  

 [!code-vb[VbFileIOWrite#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#5)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).  
  
- Der Datenträger ist voll (<xref:System.IO.IOException>).  
  
- Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist. Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung. Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [Vorgehensweise: Lesen aus Textdateien](how-to-read-from-text-files.md)
- [Schreiben in Dateien](writing-to-files.md)
