---
title: 'Vorgehensweise: Schreiben von Text in Dateien mit einem StreamWriter in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: 3b4f74836b32fea0e5c24fd4500581f17e39cd4c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623132"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a>Vorgehensweise: Schreiben von Text in Dateien mit einem StreamWriter in Visual Basic
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [Vorgehensweise: Lesen aus Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
- [Schreiben in Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
