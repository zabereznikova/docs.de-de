---
title: 'Vorgehensweise: Lesen aus einer Textdatei mit fester Breite'
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 77b2e0a4ebe36b68501f821ef5731935ee3b16a7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411628"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a>Gewusst wie: Lesen aus einer Textdatei mit fester Breite in Visual Basic

Das `TextFieldParser`-Objekt bietet eine Möglichkeit, strukturierte Textdateien wie Protokolle einfach und effizient zu analysieren.  
  
 Die `TextFieldType`-Eigenschaft definiert, ob es sich bei der analysierten Datei um eine Datei mit Trennzeichen oder mit Textfeldern fester Breite handelt. In einer Textdatei mit fester Breite kann das Feld am Ende über eine variable Breite verfügen. Um anzugeben, dass das Feld am Ende eine variable Breite besitzt, definieren Sie seine Breite kleiner als oder gleich 0 (null).  
  
### <a name="to-parse-a-fixed-width-text-file"></a>So analysieren Sie Textdatei mit fester Breite  
  
1. Erstellen Sie einen neuen `TextFieldParser`. Der folgende Code erstellt den `TextFieldParser` namens `Reader` und öffnet die Datei `test.log`.  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. Definieren Sie die `TextFieldType`-Eigenschaft als `FixedWidth`, indem Sie die Breite und das Format definieren. Der folgende Code definiert die Textspalten. Die erste ist 5 Zeichen breit, die zweite 10, die dritte 11 und die vierte ist von variabler Breite.  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. Durchlaufen Sie die Felder in der Datei. Wenn Zeilen fehlerhaft sind, melden Sie einen Fehler, und setzen Sie die Analyse fort.  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. Schließen Sie die Blöcke `While` und `Using` mit `End While` und `End Using`.  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird aus der Datei `test.log` gelesen.  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Eine Zeile kann nicht mit dem angegebenen Format analysiert werden (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). Die Ausnahmemeldung gibt die Zeile an, die die Ausnahme verursacht, während der in der Zeile enthaltene Text der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>-Eigenschaft zugewiesen wird.  
  
- Die angegebene Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
- Eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt. (<xref:System.Security.SecurityException>).  
  
- Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).  
  
- Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Gewusst wie: Lesen aus Textdateien mit Kommatrennung](how-to-read-from-comma-delimited-text-files.md)
- [Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](how-to-read-from-text-files-with-multiple-formats.md)
- [Analysieren von Textdateien mit dem TextFieldParser-Objekt](parsing-text-files-with-the-textfieldparser-object.md)
- [Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic](walkthrough-manipulating-files-and-directories.md)
- [Problembehandlung: Lesen aus und Schreiben in Textdateien](troubleshooting-reading-from-and-writing-to-text-files.md)
