---
title: 'Vorgehensweise: Lesen aus einer Textdatei (C#-Programmierleitfaden)'
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 8f79d22a86390ca931b05262e50865d852c154c7
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241746"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="0988c-102">Vorgehensweise: Lesen aus einer Textdatei (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="0988c-102">How to read from a text file (C# Programming Guide)</span></span>
<span data-ttu-id="0988c-103">In diesem Beispiel wird der Inhalt von Textdateien gelesen, indem die statische Methoden <xref:System.IO.File.ReadAllText%2A> und <xref:System.IO.File.ReadAllLines%2A> aus der <xref:System.IO.File?displayProperty=nameWithType>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0988c-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
<span data-ttu-id="0988c-104">Ein Beispiel, in dem <xref:System.IO.StreamReader> verwendet wird, finden Sie unter [Vorgehensweise: Zeilenweises Lesen einer Textdatei](./how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="0988c-104">For an example that uses <xref:System.IO.StreamReader>, see [How to read a text file one line at a time](./how-to-read-a-text-file-one-line-at-a-time.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0988c-105">Die Dateien, die in diesem Beispiel verwendet werden, werden im Thema [Vorgehensweise: Schreiben in eine Textdatei](./how-to-write-to-a-text-file.md) erstellt.</span><span class="sxs-lookup"><span data-stu-id="0988c-105">The files that are used in this example are created in the topic [How to write to a text file](./how-to-write-to-a-text-file.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="0988c-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0988c-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0988c-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0988c-107">Compiling the Code</span></span>  
 <span data-ttu-id="0988c-108">Kopieren Sie den Code, und fügen Sie ihn in eine C#-Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="0988c-108">Copy the code and paste it into a C# console application.</span></span>  
  
<span data-ttu-id="0988c-109">Wenn Sie nicht die Textdateien aus [Vorgehensweise: Schreiben in eine Textdatei](./how-to-write-to-a-text-file.md) verwenden, ersetzen Sie das Argument für `ReadAllText` und `ReadAllLines` durch die entsprechenden Pfad- und Dateinamen auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="0988c-109">If you are not using the text files from [How to write to a text file](./how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>
  
## <a name="robust-programming"></a><span data-ttu-id="0988c-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="0988c-110">Robust Programming</span></span>  
 <span data-ttu-id="0988c-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="0988c-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="0988c-112">Die Datei ist nicht oder nicht am angegebenen Speicherort vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0988c-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="0988c-113">Überprüfen Sie die Schreibweise des Dateinamens und -pfads.</span><span class="sxs-lookup"><span data-stu-id="0988c-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="0988c-114">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0988c-114">.NET Security</span></span>  
 <span data-ttu-id="0988c-115">Schließen Sie nicht vom Namen einer Datei auf deren Inhalt.</span><span class="sxs-lookup"><span data-stu-id="0988c-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="0988c-116">Bei der Datei `myFile.cs` handelt es sich zum Beispiel nicht unbedingt um eine C#-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="0988c-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0988c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0988c-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="0988c-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0988c-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0988c-119">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0988c-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
