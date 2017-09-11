---
title: 'Gewusst wie: Lesen aus durch Kommas getrennten Textdateien in Visual Basic'
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
- files, parsing
- text files, tasks
- reading text files, comma-delimited
- text files, reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
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
ms.openlocfilehash: 2ae6a3f315a8e433386319d1aa1a7f48726a19bb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="e912a-102">Gewusst wie: Lesen aus durch Kommas getrennten Textdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e912a-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="e912a-103">Das `TextFieldParser`-Objekt bietet eine Möglichkeit, strukturierte Textdateien wie Protokolle einfach und effizient zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="e912a-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="e912a-104">Die `TextFieldType`-Eigenschaft definiert, ob es sich um eine Datei mit Trennzeichen oder mit Textfeldern fester Breite handelt.</span><span class="sxs-lookup"><span data-stu-id="e912a-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="e912a-105">Analysieren einer durch Trennzeichen getrennten Textdatei</span><span class="sxs-lookup"><span data-stu-id="e912a-105">To parse a comma delimited text file</span></span>  
  
1.  <span data-ttu-id="e912a-106">Erstellen Sie einen neuen `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="e912a-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="e912a-107">Der folgende Code erstellt den `TextFieldParser` namens `MyReader` und öffnet die Datei `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="e912a-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     <span data-ttu-id="e912a-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e912a-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span></span>  
  
2.  <span data-ttu-id="e912a-109">Definieren Sie den `TextField`-Typ und das Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="e912a-109">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="e912a-110">Der folgende Code definiert die `TextFieldType`-Eigenschaft als `Delimited` und das Trennzeichen als „,“.</span><span class="sxs-lookup"><span data-stu-id="e912a-110">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     <span data-ttu-id="e912a-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e912a-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span></span>  
  
3.  <span data-ttu-id="e912a-112">Durchlaufen Sie die Felder in der Datei.</span><span class="sxs-lookup"><span data-stu-id="e912a-112">Loop through the fields in the file.</span></span> <span data-ttu-id="e912a-113">Wenn Zeilen fehlerhaft sind, einen Fehler melden und die Analyse fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="e912a-113">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="e912a-114">Der folgende Code durchläuft die Datei, zeigt der Reihe nach jedes Feld an und meldet alle Felder, die nicht korrekt formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="e912a-114">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     <span data-ttu-id="e912a-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e912a-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span></span>  
  
4.  <span data-ttu-id="e912a-116">Schließen Sie die Blöcke `While` und `Using` mit `End While` und `End Using`.</span><span class="sxs-lookup"><span data-stu-id="e912a-116">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     <span data-ttu-id="e912a-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e912a-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e912a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e912a-118">Example</span></span>  
 <span data-ttu-id="e912a-119">In diesem Beispiel wird aus der Datei `test.txt` gelesen.</span><span class="sxs-lookup"><span data-stu-id="e912a-119">This example reads from the file `test.txt`.</span></span>  
  
 <span data-ttu-id="e912a-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e912a-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e912a-121">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="e912a-121">Robust programming</span></span>  
 <span data-ttu-id="e912a-122">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="e912a-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e912a-123">Eine Zeile kann nicht mit dem angegebenen Format analysiert werden (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="e912a-123">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="e912a-124">Die Ausnahmemeldung gibt die Zeile an, die die Ausnahme verursacht, während der in der Zeile enthaltene Text der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>-Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e912a-124">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
-   <span data-ttu-id="e912a-125">Die angegebene Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="e912a-125">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="e912a-126">Eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="e912a-126">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="e912a-127">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e912a-127">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="e912a-128">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="e912a-128">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="e912a-129">Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="e912a-129">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e912a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e912a-130">See also</span></span>  
 <span data-ttu-id="e912a-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e912a-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="e912a-132">[Gewusst wie: Lesen aus einer Textdatei mit fester Breite](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="e912a-132">[How to: Read From Fixed-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span></span>  
 <span data-ttu-id="e912a-133">[Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="e912a-133">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 <span data-ttu-id="e912a-134">[Analysieren von Textdateien mit dem TextFieldParser-Objekt](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span><span class="sxs-lookup"><span data-stu-id="e912a-134">[Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span></span>  
 <span data-ttu-id="e912a-135">[Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="e912a-135">[Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span></span>  
 [<span data-ttu-id="e912a-136">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="e912a-136">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)

