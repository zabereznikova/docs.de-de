---
title: 'Vorgehensweise: Lesen aus einer Textdatei – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 560453a81124a3ee52a2ffd794ddac026c7394a5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978019"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="6d879-102">Vorgehensweise: Lesen aus einer Textdatei (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6d879-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="6d879-103">In diesem Beispiel wird der Inhalt von Textdateien gelesen, indem die statische Methoden <xref:System.IO.File.ReadAllText%2A> und <xref:System.IO.File.ReadAllLines%2A> aus der <xref:System.IO.File?displayProperty=nameWithType>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d879-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="6d879-104">Ein Beispiel, in dem <xref:System.IO.StreamReader> verwendet wird, finden Sie unter [Vorgehensweise: Zeilenweises Lesen einer Textdatei](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="6d879-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d879-105">Die in diesem Beispiel verwendeten Dateien werden in diesem Thema beschrieben: [Vorgehensweise: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="6d879-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d879-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d879-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6d879-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6d879-107">Compiling the Code</span></span>  
 <span data-ttu-id="6d879-108">Kopieren Sie den Code, und fügen Sie ihn in eine C#-Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="6d879-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="6d879-109">Wenn Sie nicht die Textdateien aus [Vorgehensweise: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) verwenden, ersetzen Sie das Argument für `ReadAllText` und `ReadAllLines` durch die entsprechenden Pfad- und Dateinamen auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="6d879-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6d879-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6d879-110">Robust Programming</span></span>  
 <span data-ttu-id="6d879-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="6d879-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6d879-112">Die Datei ist nicht oder nicht am angegebenen Speicherort vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6d879-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="6d879-113">Überprüfen Sie die Schreibweise des Dateinamens und -pfads.</span><span class="sxs-lookup"><span data-stu-id="6d879-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6d879-114">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6d879-114">.NET Framework Security</span></span>  
 <span data-ttu-id="6d879-115">Schließen Sie nicht vom Namen einer Datei auf deren Inhalt.</span><span class="sxs-lookup"><span data-stu-id="6d879-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="6d879-116">Bei der Datei `myFile.cs` handelt es sich zum Beispiel nicht unbedingt um eine C#-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="6d879-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d879-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d879-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="6d879-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6d879-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6d879-119">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6d879-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
