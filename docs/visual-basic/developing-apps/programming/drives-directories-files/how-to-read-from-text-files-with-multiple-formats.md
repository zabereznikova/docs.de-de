---
title: 'Vorgehensweise: Lesen aus Textdateien mit mehreren Formaten in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method [Visual Basic], parsing structured text files
- PeekChars method [Visual Basic], determining format of text
- reading text files [Visual Basic], multiple formats
- I/O [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
ms.openlocfilehash: 9fa484f0a74d900bd6f0365f2ce71fd32e1422db
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623181"
---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a><span data-ttu-id="7029b-102">Vorgehensweise: Lesen aus Textdateien mit mehreren Formaten in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7029b-102">How to: Read From Text Files with Multiple Formats in Visual Basic</span></span>
<span data-ttu-id="7029b-103">Das <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>-Objekt bietet eine Möglichkeit, strukturierte Textdateien wie Protokolle einfach und effizient zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="7029b-103">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="7029b-104">Sie können eine Datei mit mehreren Formaten verarbeiten, indem Sie die `PeekChars`-Methode verwenden, um das Format jeder Zeile zu bestimmen, während Sie eine Datei analysieren.</span><span class="sxs-lookup"><span data-stu-id="7029b-104">You can process a file with multiple formats by using the `PeekChars` method to determine the format of each line as you parse through the file.</span></span>  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a><span data-ttu-id="7029b-105">Analysieren einen Textdatei mit mehreren Formaten</span><span class="sxs-lookup"><span data-stu-id="7029b-105">To parse a text file with multiple formats</span></span>  
  
1. <span data-ttu-id="7029b-106">Fügen Sie eine Textdatei mit dem Namen „textfile.txt“ in Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="7029b-106">Add a text file named testfile.txt to your project.</span></span> <span data-ttu-id="7029b-107">Fügen Sie folgenden Inhalt in der Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="7029b-107">Add the following content to the text file.</span></span>  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2. <span data-ttu-id="7029b-108">Definieren Sie das erwartete Format und das Format, das verwendet werden soll, wenn ein Fehler gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="7029b-108">Define the expected format and the format used when an error is reported.</span></span> <span data-ttu-id="7029b-109">Der letzte Eintrag in jedem Array ist -1. Deshalb wird davon ausgegangen, dass das letzte Feld von variabler Breite ist.</span><span class="sxs-lookup"><span data-stu-id="7029b-109">The last entry in each array is -1, therefore the last field is assumed to be of variable width.</span></span> <span data-ttu-id="7029b-110">Dies tritt auf, wenn der letzte Eintrag des Arrays weniger oder gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="7029b-110">This occurs when the last entry in the array is less than or equal to 0.</span></span>  
  
     [!code-vb[VbFileIORead#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#4)]  
  
3. <span data-ttu-id="7029b-111">Erstellen Sie ein neues <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>-Objekt, das die Breite und das Format definiert.</span><span class="sxs-lookup"><span data-stu-id="7029b-111">Create a new <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object, defining the width and format.</span></span>  
  
     [!code-vb[VbFileIORead#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#5)]  
  
4. <span data-ttu-id="7029b-112">Gehen Sie durch die Reihen, und prüfen Sie vor dem Lesen das Format.</span><span class="sxs-lookup"><span data-stu-id="7029b-112">Loop through the rows, testing for format before reading.</span></span>  
  
     [!code-vb[VbFileIORead#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#6)]  
  
5. <span data-ttu-id="7029b-113">Schreiben Sie Fehler in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="7029b-113">Write errors to the console.</span></span>  
  
     [!code-vb[VbFileIORead#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="7029b-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7029b-114">Example</span></span>  
 <span data-ttu-id="7029b-115">Unten stehend finden Sie das vollständige Beispiel, das aus der `testfile.txt`-Datei liest.</span><span class="sxs-lookup"><span data-stu-id="7029b-115">Following is the complete example that reads from the file `testfile.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="7029b-116">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="7029b-116">Robust Programming</span></span>  
 <span data-ttu-id="7029b-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="7029b-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="7029b-118">Eine Zeile kann nicht mit dem angegebenen Format analysiert werden (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="7029b-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="7029b-119">Die Ausnahmemeldung gibt die Zeile an, die die Ausnahme verursacht, während der in der Zeile enthaltene Text der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>-Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7029b-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="7029b-120">Die angegebene Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="7029b-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="7029b-121">Eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="7029b-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="7029b-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="7029b-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="7029b-123">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="7029b-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="7029b-124">Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="7029b-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7029b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7029b-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- [<span data-ttu-id="7029b-126">Vorgehensweise: Lesen aus durch Trennzeichen getrennten Textdateien</span><span class="sxs-lookup"><span data-stu-id="7029b-126">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="7029b-127">Vorgehensweise: Lesen aus einer Textdatei mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="7029b-127">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="7029b-128">Analysieren von Textdateien mit dem TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="7029b-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
