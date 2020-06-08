---
title: Analysieren von Textdateien mit dem TextFieldParser-Objekt
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files [Visual Basic], parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
ms.openlocfilehash: 7b2cb0dd39d14dd94db661cc9cbacf99edf0e778
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406676"
---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a>Analysieren von Textdateien mit dem TextFieldParser-Objekt (Visual Basic)

Das `TextFieldParser`-Objekt erlaubt Ihnen, sehr große Dateien zu analysieren und zu bearbeiten, die als Text mit getrennter Spaltenbreite strukturiert sind, wie Protokolldateien oder ältere Datenbankinformationen. Das Analysieren einer Textdatei mit `TextFieldParser` ähnelt dem Durchlaufen einer Textdatei, während die Analysemethode zum Extrahieren von Textfeldern den Methoden zur Zeichenfolgenbearbeitung ähnelt, die verwendet werden, um gesperrte Zeichenfolgen mit Token zu erstellen.  
  
## <a name="parsing-different-types-of-text-files"></a>Analysieren von verschiedenen Typen von Textdateien  

 Textdateien können Felder verschiedener Breite besitzen, die durch ein Zeichen wie ein Komma oder ein Tabstoppzeichen getrennt wurden. Definieren Sie `TextFieldType` und das Trennzeichen wie im folgenden Beispiel, das die `SetDelimiters`-Methode verwendet, um eine durch Tabstoppzeichen getrennte Textdatei zu definieren:  
  
 [!code-vb[VbVbalrTextFieldParser#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#21)]  
  
 Andere Textdateien haben vielleicht feste Feldbreiten. In solchen Fällen müssen Sie den `TextFieldType` als `FixedWidth` sowie die Breite jedes Felds definieren, wie im folgenden Beispiel gezeigt. In diesem Beispiel wird die `SetFieldWidths`-Methode verwendet, um die Textspalten zu definieren: Die erste Spalte ist 5 Zeichen breit, die zweite 10, die dritte 11 und die vierte ist von variabler Breite.  
  
 [!code-vb[VbVbalrTextFieldParser#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#22)]  
  
 Sobald das Format definiert ist, können Sie Dateien mithilfe der `ReadFields`-Methode durchlaufen, um jede Zeile einzeln zu verarbeiten.  
  
 Wenn ein Feld nicht dem angegebenen Format entspricht, wird eine <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>-Ausnahme ausgelöst. Wenn diese Ausnahmen ausgelöst werden, enthalten die Eigenschaften `ErrorLine` und `ErrorLineNumber` den Text, der die Ausnahme auslöst, sowie die Zeilennummer des Texts.  
  
## <a name="parsing-files-with-multiple-formats"></a>Analysieren von Dateien mit mehreren Formaten  

 Die `PeekChars`-Methode des `TextFieldParser`-Objekts kann verwendet werden, um jede Datei vor dem Lesen zu überprüfen, was Ihnen erlaubt, mehrere Formate für die Felder zu definieren und entsprechend darauf zu reagieren. Weitere Informationen finden Sie unter [Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](how-to-read-from-text-files-with-multiple-formats.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>
