---
title: Analysieren von Textdateien mit dem TextFieldParser-Objekt (Visual Basic)
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
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files, parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ad7407ca1928f9b4a2405bc5831777fbf965b61f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="da51f-102">Analysieren von Textdateien mit dem TextFieldParser-Objekt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da51f-102">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>
<span data-ttu-id="da51f-103">Das `TextFieldParser`-Objekt erlaubt Ihnen, sehr große Dateien zu analysieren und zu bearbeiten, die als Text mit getrennter Spaltenbreite strukturiert sind, wie Protokolldateien oder ältere Datenbankinformationen.</span><span class="sxs-lookup"><span data-stu-id="da51f-103">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="da51f-104">Das Analysieren einer Textdatei mit `TextFieldParser` ähnelt dem Durchlaufen einer Textdatei, während die Analysemethode zum Extrahieren von Textfeldern den Methoden zur Zeichenfolgenbearbeitung ähnelt, die verwendet werden, um gesperrte Zeichenfolgen mit Token zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da51f-104">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="da51f-105">Analysieren von verschiedenen Typen von Textdateien</span><span class="sxs-lookup"><span data-stu-id="da51f-105">Parsing different types of text files</span></span>  
 <span data-ttu-id="da51f-106">Textdateien können Felder verschiedener Breite besitzen, die durch ein Zeichen wie ein Komma oder ein Tabstoppzeichen getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="da51f-106">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="da51f-107">Definieren Sie `TextFieldType` und das Trennzeichen wie im folgenden Beispiel, das die `SetDelimiters`-Methode verwendet, um eine durch Tabstoppzeichen getrennte Textdatei zu definieren:</span><span class="sxs-lookup"><span data-stu-id="da51f-107">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 <span data-ttu-id="da51f-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="da51f-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span></span>  
  
 <span data-ttu-id="da51f-109">Andere Textdateien haben vielleicht feste Feldbreiten.</span><span class="sxs-lookup"><span data-stu-id="da51f-109">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="da51f-110">In solchen Fällen müssen Sie den `TextFieldType` als `FixedWidth` sowie die Breite jedes Felds definieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="da51f-110">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="da51f-111">In diesem Beispiel wird die `SetFieldWidths`-Methode verwendet, um die Textspalten zu definieren: Die erste Spalte ist 5 Zeichen breit, die zweite 10, die dritte 11 und die vierte ist von variabler Breite.</span><span class="sxs-lookup"><span data-stu-id="da51f-111">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 <span data-ttu-id="da51f-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="da51f-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span></span>  
  
 <span data-ttu-id="da51f-113">Sobald das Format definiert ist, können Sie Dateien mithilfe der `ReadFields`-Methode durchlaufen, um jede Zeile einzeln zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="da51f-113">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="da51f-114">Wenn ein Feld nicht dem angegebenen Format entspricht, wird eine <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="da51f-114">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="da51f-115">Wenn diese Ausnahmen ausgelöst werden, enthalten die Eigenschaften `ErrorLine` und `ErrorLineNumber` den Text, der die Ausnahme auslöst, sowie die Zeilennummer des Texts.</span><span class="sxs-lookup"><span data-stu-id="da51f-115">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="da51f-116">Analysieren von Dateien mit mehreren Formaten</span><span class="sxs-lookup"><span data-stu-id="da51f-116">Parsing files with multiple formats</span></span>  
 <span data-ttu-id="da51f-117">Die `PeekChars`-Methode des `TextFieldParser`-Objekts kann verwendet werden, um jede Datei vor dem Lesen zu überprüfen, was Ihnen erlaubt, mehrere Formate für die Felder zu definieren und entsprechend darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="da51f-117">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="da51f-118">Weitere Informationen finden Sie unter [Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span><span class="sxs-lookup"><span data-stu-id="da51f-118">For more information, see [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da51f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da51f-119">See also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>

