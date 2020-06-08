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
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="6f1d6-102">Analysieren von Textdateien mit dem TextFieldParser-Objekt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f1d6-102">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>

<span data-ttu-id="6f1d6-103">Das `TextFieldParser`-Objekt erlaubt Ihnen, sehr große Dateien zu analysieren und zu bearbeiten, die als Text mit getrennter Spaltenbreite strukturiert sind, wie Protokolldateien oder ältere Datenbankinformationen.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-103">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="6f1d6-104">Das Analysieren einer Textdatei mit `TextFieldParser` ähnelt dem Durchlaufen einer Textdatei, während die Analysemethode zum Extrahieren von Textfeldern den Methoden zur Zeichenfolgenbearbeitung ähnelt, die verwendet werden, um gesperrte Zeichenfolgen mit Token zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-104">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="6f1d6-105">Analysieren von verschiedenen Typen von Textdateien</span><span class="sxs-lookup"><span data-stu-id="6f1d6-105">Parsing different types of text files</span></span>  

 <span data-ttu-id="6f1d6-106">Textdateien können Felder verschiedener Breite besitzen, die durch ein Zeichen wie ein Komma oder ein Tabstoppzeichen getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-106">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="6f1d6-107">Definieren Sie `TextFieldType` und das Trennzeichen wie im folgenden Beispiel, das die `SetDelimiters`-Methode verwendet, um eine durch Tabstoppzeichen getrennte Textdatei zu definieren:</span><span class="sxs-lookup"><span data-stu-id="6f1d6-107">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#21)]  
  
 <span data-ttu-id="6f1d6-108">Andere Textdateien haben vielleicht feste Feldbreiten.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-108">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="6f1d6-109">In solchen Fällen müssen Sie den `TextFieldType` als `FixedWidth` sowie die Breite jedes Felds definieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-109">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="6f1d6-110">In diesem Beispiel wird die `SetFieldWidths`-Methode verwendet, um die Textspalten zu definieren: Die erste Spalte ist 5 Zeichen breit, die zweite 10, die dritte 11 und die vierte ist von variabler Breite.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-110">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#22)]  
  
 <span data-ttu-id="6f1d6-111">Sobald das Format definiert ist, können Sie Dateien mithilfe der `ReadFields`-Methode durchlaufen, um jede Zeile einzeln zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-111">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="6f1d6-112">Wenn ein Feld nicht dem angegebenen Format entspricht, wird eine <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-112">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="6f1d6-113">Wenn diese Ausnahmen ausgelöst werden, enthalten die Eigenschaften `ErrorLine` und `ErrorLineNumber` den Text, der die Ausnahme auslöst, sowie die Zeilennummer des Texts.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-113">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="6f1d6-114">Analysieren von Dateien mit mehreren Formaten</span><span class="sxs-lookup"><span data-stu-id="6f1d6-114">Parsing files with multiple formats</span></span>  

 <span data-ttu-id="6f1d6-115">Die `PeekChars`-Methode des `TextFieldParser`-Objekts kann verwendet werden, um jede Datei vor dem Lesen zu überprüfen, was Ihnen erlaubt, mehrere Formate für die Felder zu definieren und entsprechend darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="6f1d6-115">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="6f1d6-116">Weitere Informationen finden Sie unter [Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](how-to-read-from-text-files-with-multiple-formats.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d6-116">For more information, see [How to: Read From Text Files with Multiple Formats](how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1d6-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f1d6-117">See also</span></span>

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
