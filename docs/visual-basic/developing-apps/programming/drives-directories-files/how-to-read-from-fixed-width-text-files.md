---
title: 'Vorgehensweise: Lesen aus einer Textdatei mit fester Breite in Visual Basic'
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
- fixed-width text file
- reading text files, fixed-width
- files, parsing
- text files, tasks
- text files, reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: 24
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
ms.openlocfilehash: fc45c6d6e4301b2786fefe947ed011ca95f8a79c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="526ab-102">Gewusst wie: Lesen aus einer Textdatei mit fester Breite in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="526ab-102">How to: read from fixed-width text files in Visual Basic</span></span>
<span data-ttu-id="526ab-103">Das `TextFieldParser`-Objekt bietet eine Möglichkeit, strukturierte Textdateien wie Protokolle einfach und effizient zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="526ab-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="526ab-104">Die `TextFieldType`-Eigenschaft definiert, ob es sich bei der analysierten Datei um eine Datei mit Trennzeichen oder mit Textfeldern fester Breite handelt.</span><span class="sxs-lookup"><span data-stu-id="526ab-104">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="526ab-105">In einer Textdatei mit fester Breite kann das Feld am Ende über eine variable Breite verfügen.</span><span class="sxs-lookup"><span data-stu-id="526ab-105">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="526ab-106">Um anzugeben, dass das Feld am Ende eine variable Breite besitzt, definieren Sie seine Breite kleiner als oder gleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="526ab-106">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="526ab-107">So analysieren Sie Textdatei mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="526ab-107">To parse a fixed-width text file</span></span>  
  
1.  <span data-ttu-id="526ab-108">Erstellen Sie einen neuen `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="526ab-108">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="526ab-109">Der folgende Code erstellt den `TextFieldParser` namens `Reader` und öffnet die Datei `test.log`.</span><span class="sxs-lookup"><span data-stu-id="526ab-109">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     <span data-ttu-id="526ab-110">[!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="526ab-110">[!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]</span></span>  
  
2.  <span data-ttu-id="526ab-111">Definieren Sie die `TextFieldType`-Eigenschaft als `FixedWidth`, indem Sie die Breite und das Format definieren.</span><span class="sxs-lookup"><span data-stu-id="526ab-111">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="526ab-112">Der folgende Code definiert die Textspalten. Die erste ist 5 Zeichen breit, die zweite 10, die dritte 11 und die vierte ist von variabler Breite.</span><span class="sxs-lookup"><span data-stu-id="526ab-112">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     <span data-ttu-id="526ab-113">[!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="526ab-113">[!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]</span></span>  
  
3.  <span data-ttu-id="526ab-114">Führen Sie eine Iteration auf die Felder in der Datei aus.</span><span class="sxs-lookup"><span data-stu-id="526ab-114">Loop through the fields in the file.</span></span> <span data-ttu-id="526ab-115">Wenn Zeilen fehlerhaft sind, melden Sie einen Fehler, und setzen Sie die Analyse fort.</span><span class="sxs-lookup"><span data-stu-id="526ab-115">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     <span data-ttu-id="526ab-116">[!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="526ab-116">[!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]</span></span>  
  
4.  <span data-ttu-id="526ab-117">Schließen Sie die Blöcke `While` und `Using` mit `End While` und `End Using`.</span><span class="sxs-lookup"><span data-stu-id="526ab-117">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     <span data-ttu-id="526ab-118">[!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="526ab-118">[!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="526ab-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="526ab-119">Example</span></span>  
 <span data-ttu-id="526ab-120">In diesem Beispiel wird aus der Datei `test.log` gelesen.</span><span class="sxs-lookup"><span data-stu-id="526ab-120">This example reads from the file `test.log`.</span></span>  
  
 <span data-ttu-id="526ab-121">[!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="526ab-121">[!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="526ab-122">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="526ab-122">Robust programming</span></span>  
 <span data-ttu-id="526ab-123">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="526ab-123">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="526ab-124">Eine Zeile kann nicht mit dem angegebenen Format analysiert werden (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="526ab-124">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="526ab-125">Die Ausnahmemeldung gibt die Zeile an, die die Ausnahme verursacht, während der in der Zeile enthaltene Text der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>-Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="526ab-125">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
-   <span data-ttu-id="526ab-126">Die angegebene Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="526ab-126">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="526ab-127">Eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="526ab-127">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="526ab-128">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="526ab-128">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="526ab-129">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="526ab-129">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="526ab-130">Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="526ab-130">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526ab-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="526ab-131">See also</span></span>  
 <span data-ttu-id="526ab-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="526ab-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="526ab-133">[Gewusst wie: Lesen aus durch Kommas getrennten Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="526ab-133">[How to: Read From Comma-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span></span>  
 <span data-ttu-id="526ab-134">[Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="526ab-134">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 <span data-ttu-id="526ab-135">[Analysieren von Textdateien mit dem TextFieldParser-Objekt](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span><span class="sxs-lookup"><span data-stu-id="526ab-135">[Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span></span>  
 <span data-ttu-id="526ab-136">[Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="526ab-136">[Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span></span>  
 [<span data-ttu-id="526ab-137">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="526ab-137">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 

