---
title: 'Gewusst wie: Lesen aus einer Textdatei (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- StreamReader.ReadToEnd
dev_langs:
- CSharp
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: bd0ad3e062c4d4b32fb6140cacba9a4a32674759
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="8d530-102">Gewusst wie: Lesen aus einer Textdatei (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8d530-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="8d530-103">In diesem Beispiel wird der Inhalt von Textdateien gelesen, indem die statische Methoden <xref:System.IO.File.ReadAllText%2A> und <xref:System.IO.File.ReadAllLines%2A> aus der <xref:System.IO.File?displayProperty=fullName>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8d530-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=fullName> class.</span></span>  
  
 <span data-ttu-id="8d530-104">Ein Beispiel, in dem <xref:System.IO.StreamReader> verwendet wird, finden Sie unter [Vorgehensweise: Zeilenweises Lesen einer Textdatei](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="8d530-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d530-105">Die Dateien, die in diesem Beispiel verwendet werden, werden im Thema [Vorgehensweise: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) erstellt.</span><span class="sxs-lookup"><span data-stu-id="8d530-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d530-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d530-106">Example</span></span>  
 <span data-ttu-id="8d530-107">[!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8d530-107">[!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d530-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8d530-108">Compiling the Code</span></span>  
 <span data-ttu-id="8d530-109">Kopieren Sie den Code, und fügen Sie ihn in eine C#-Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="8d530-109">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="8d530-110">Wenn Sie nicht die Textdateien aus [Vorgehensweise: Schreiben in eine Textdatei](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) verwenden, ersetzen Sie das Argument für `ReadAllText` und `ReadAllLines` durch die entsprechenden Pfad- und Dateinamen auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="8d530-110">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8d530-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8d530-111">Robust Programming</span></span>  
 <span data-ttu-id="8d530-112">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="8d530-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8d530-113">Die Datei ist nicht oder nicht am angegebenen Speicherort vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8d530-113">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="8d530-114">Überprüfen Sie die Schreibweise des Dateinamens und -pfads.</span><span class="sxs-lookup"><span data-stu-id="8d530-114">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8d530-115">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8d530-115">.NET Framework Security</span></span>  
 <span data-ttu-id="8d530-116">Schließen Sie nicht vom Namen einer Datei auf deren Inhalt.</span><span class="sxs-lookup"><span data-stu-id="8d530-116">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="8d530-117">Bei der Datei `myFile.cs` handelt es sich zum Beispiel nicht unbedingt um eine C#-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="8d530-117">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d530-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d530-118">See Also</span></span>  
 <span data-ttu-id="8d530-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8d530-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="8d530-120">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d530-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8d530-121">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8d530-121">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

