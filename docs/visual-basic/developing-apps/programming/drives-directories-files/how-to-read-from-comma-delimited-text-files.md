---
title: 'Vorgehensweise: Lesen aus durch Kommas getrennten Textdateien'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: 9b93893e2221b156b65ce8e945089269ea28c989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335064"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="7669e-102">Gewusst wie: Lesen aus durch Kommas getrennten Textdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7669e-102">How to: read from comma-delimited text files in Visual Basic</span></span>

<span data-ttu-id="7669e-103">Das `TextFieldParser`-Objekt bietet eine Möglichkeit, strukturierte Textdateien wie Protokolle einfach und effizient zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="7669e-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="7669e-104">Die `TextFieldType`-Eigenschaft definiert, ob es sich um eine Datei mit Trennzeichen oder mit Textfeldern fester Breite handelt.</span><span class="sxs-lookup"><span data-stu-id="7669e-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="7669e-105">Analysieren einer durch Trennzeichen getrennten Textdatei</span><span class="sxs-lookup"><span data-stu-id="7669e-105">To parse a comma delimited text file</span></span>  
  
1. <span data-ttu-id="7669e-106">Erstellen Sie einen neuen `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="7669e-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="7669e-107">Der folgende Code erstellt den `TextFieldParser` namens `MyReader` und öffnet die Datei `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="7669e-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2. <span data-ttu-id="7669e-108">Definieren Sie den `TextField`-Typ und das Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="7669e-108">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="7669e-109">Der folgende Code definiert die `TextFieldType`-Eigenschaft als `Delimited` und das Trennzeichen als „,“.</span><span class="sxs-lookup"><span data-stu-id="7669e-109">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3. <span data-ttu-id="7669e-110">Durchlaufen Sie die Felder in der Datei.</span><span class="sxs-lookup"><span data-stu-id="7669e-110">Loop through the fields in the file.</span></span> <span data-ttu-id="7669e-111">Wenn Zeilen fehlerhaft sind, einen Fehler melden und die Analyse fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="7669e-111">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="7669e-112">Der folgende Code durchläuft die Datei, zeigt der Reihe nach jedes Feld an und meldet alle Felder, die nicht korrekt formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="7669e-112">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4. <span data-ttu-id="7669e-113">Schließen Sie die Blöcke `While` und `Using` mit `End While` und `End Using`.</span><span class="sxs-lookup"><span data-stu-id="7669e-113">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a><span data-ttu-id="7669e-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7669e-114">Example</span></span>  

 <span data-ttu-id="7669e-115">In diesem Beispiel wird aus der Datei `test.txt` gelesen.</span><span class="sxs-lookup"><span data-stu-id="7669e-115">This example reads from the file `test.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="7669e-116">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="7669e-116">Robust programming</span></span>  

 <span data-ttu-id="7669e-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="7669e-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="7669e-118">Eine Zeile kann nicht mit dem angegebenen Format analysiert werden (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="7669e-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="7669e-119">Die Ausnahmemeldung gibt die Zeile an, die die Ausnahme verursacht, während der in der Zeile enthaltene Text der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>-Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7669e-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
- <span data-ttu-id="7669e-120">Die angegebene Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="7669e-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="7669e-121">Eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Dateizugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="7669e-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="7669e-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="7669e-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="7669e-123">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="7669e-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="7669e-124">Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="7669e-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7669e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7669e-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="7669e-126">Gewusst wie: Lesen aus einer Textdatei mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="7669e-126">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="7669e-127">Gewusst wie: Lesen aus Textdateien mit mehreren Formaten</span><span class="sxs-lookup"><span data-stu-id="7669e-127">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="7669e-128">Analysieren von Textdateien mit dem TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="7669e-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="7669e-129">Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7669e-129">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="7669e-130">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="7669e-130">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
