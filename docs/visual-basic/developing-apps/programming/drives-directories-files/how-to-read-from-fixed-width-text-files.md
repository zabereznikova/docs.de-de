---
title: 'Vorgehensweise: Lesen aus einer Textdatei mit fester Breite in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: c777e54f2857e32f1f00460c17b988c597506ad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588673"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="6ceb9-102">Gewusst wie: Lesen aus einer Textdatei mit fester Breite in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ceb9-102">How to: read from fixed-width text files in Visual Basic</span></span>
<span data-ttu-id="6ceb9-103">Das `TextFieldParser`-Objekt bietet eine Möglichkeit, strukturierte Textdateien wie Protokolle einfach und effizient zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="6ceb9-104">Die `TextFieldType`-Eigenschaft definiert, ob es sich bei der analysierten Datei um eine Datei mit Trennzeichen oder mit Textfeldern fester Breite handelt.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-104">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="6ceb9-105">In einer Textdatei mit fester Breite kann das Feld am Ende über eine variable Breite verfügen.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-105">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="6ceb9-106">Um anzugeben, dass das Feld am Ende eine variable Breite besitzt, definieren Sie seine Breite kleiner als oder gleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="6ceb9-106">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="6ceb9-107">So analysieren Sie Textdatei mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="6ceb9-107">To parse a fixed-width text file</span></span>  
  
1.  <span data-ttu-id="6ceb9-108">Erstellen Sie einen neuen `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-108">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="6ceb9-109">Der folgende Code erstellt den `TextFieldParser` namens `Reader` und öffnet die Datei `test.log`.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-109">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     [!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]  
  
2.  <span data-ttu-id="6ceb9-110">Definieren Sie die `TextFieldType`-Eigenschaft als `FixedWidth`, indem Sie die Breite und das Format definieren.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-110">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="6ceb9-111">Der folgende Code definiert die Textspalten. Die erste ist 5 Zeichen breit, die zweite 10, die dritte 11 und die vierte ist von variabler Breite.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-111">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     [!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]  
  
3.  <span data-ttu-id="6ceb9-112">Durchlaufen Sie die Felder in der Datei.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-112">Loop through the fields in the file.</span></span> <span data-ttu-id="6ceb9-113">Wenn Zeilen fehlerhaft sind, melden Sie einen Fehler, und setzen Sie die Analyse fort.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-113">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     [!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]  
  
4.  <span data-ttu-id="6ceb9-114">Schließen Sie die Blöcke `While` und `Using` mit `End While` und `End Using`.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-114">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="6ceb9-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ceb9-115">Example</span></span>  
 <span data-ttu-id="6ceb9-116">In diesem Beispiel wird aus der Datei `test.log` gelesen.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-116">This example reads from the file `test.log`.</span></span>  
  
 [!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6ceb9-117">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6ceb9-117">Robust programming</span></span>  
 <span data-ttu-id="6ceb9-118">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="6ceb9-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6ceb9-119">Eine Zeile kann nicht mit dem angegebenen Format analysiert werden (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="6ceb9-119">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="6ceb9-120">Die Ausnahmemeldung gibt die Zeile an, die die Ausnahme verursacht, während der in der Zeile enthaltene Text der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>-Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-120">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
-   <span data-ttu-id="6ceb9-121">Die angegebene Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="6ceb9-121">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="6ceb9-122">Eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="6ceb9-122">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="6ceb9-123">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="6ceb9-123">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="6ceb9-124">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="6ceb9-124">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="6ceb9-125">Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="6ceb9-125">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ceb9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ceb9-126">See also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>  
 [<span data-ttu-id="6ceb9-127">Gewusst wie: Lesen aus Textdateien mit Kommatrennung</span><span class="sxs-lookup"><span data-stu-id="6ceb9-127">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [<span data-ttu-id="6ceb9-128">Gewusst wie: Lesen aus Textdateien mit mehreren Formaten</span><span class="sxs-lookup"><span data-stu-id="6ceb9-128">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)  
 [<span data-ttu-id="6ceb9-129">Analysieren von Textdateien mit dem TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="6ceb9-129">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [<span data-ttu-id="6ceb9-130">Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ceb9-130">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 [<span data-ttu-id="6ceb9-131">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="6ceb9-131">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 
