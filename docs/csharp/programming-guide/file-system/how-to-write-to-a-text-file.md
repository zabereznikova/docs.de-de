---
title: 'Vorgehensweise: Schreiben in eine Textdatei (C#-Programmierleitfaden)'
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ac16fb971eae5654a55e2f1753d78a6458f03315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712246"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="72092-102">Vorgehensweise: Schreiben in eine Textdatei (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="72092-102">How to write to a text file (C# Programming Guide)</span></span>
<span data-ttu-id="72092-103">In diesen Beispielen werden verschiedene Möglichkeiten veranschaulicht, Text in eine Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="72092-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="72092-104">In den ersten beiden Beispielen werden statische Hilfsmethoden für die <xref:System.IO.File?displayProperty=nameWithType>-Klasse verwendet, um jedes Element von `IEnumerable<string>` und eine Zeichenfolge in eine Textdatei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="72092-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="72092-105">In Beispiel 3 wird dargestellt, wie Text einer Datei hinzugefügt wird, wenn jede Zeile beim Schreiben in die Datei einzeln verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="72092-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="72092-106">Die Beispiele 1–3 überschreiben alle vorhandenen Inhalte in der Datei. In Beispiel 4 wird jedoch gezeigt, wie einer vorhandenen Datei Text angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="72092-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="72092-107">In jedem Beispiel werden Zeichenfolgenliterale in Dateien geschrieben.</span><span class="sxs-lookup"><span data-stu-id="72092-107">These examples all write string literals to files.</span></span> <span data-ttu-id="72092-108">Wenn Sie Text formatieren wollen, der in eine Datei geschrieben wird, verwenden Sie die <xref:System.String.Format%2A>-Methode oder das C#-Feature [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="72092-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72092-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72092-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="72092-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="72092-110">Robust Programming</span></span>  
 <span data-ttu-id="72092-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="72092-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="72092-112">Die Datei ist bereits vorhanden und ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="72092-112">The file exists and is read-only.</span></span>  
  
- <span data-ttu-id="72092-113">Der Pfadname ist möglicherweise zu lang.</span><span class="sxs-lookup"><span data-stu-id="72092-113">The path name may be too long.</span></span>  
  
- <span data-ttu-id="72092-114">Der Datenträger ist möglicherweise voll.</span><span class="sxs-lookup"><span data-stu-id="72092-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72092-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72092-115">See also</span></span>

- [<span data-ttu-id="72092-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="72092-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="72092-117">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="72092-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="72092-118">Beispiel: Speichern einer Auflistung im Anwendungsspeicher</span><span class="sxs-lookup"><span data-stu-id="72092-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
