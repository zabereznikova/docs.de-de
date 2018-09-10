---
title: 'Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bea51eaf11bd9d73d5a68eb09795bd9f9f143f95
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44214471"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="932c6-102">Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="932c6-102">How to: Write Characters to a String</span></span>
<span data-ttu-id="932c6-103">In den folgenden Codebeispielen werden Zeichen synchron und asynchron aus einem Zeichenarray in eine Zeichenfolge geschrieben.</span><span class="sxs-lookup"><span data-stu-id="932c6-103">The following code examples write characters synchronously and asynchronously from a character array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="932c6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="932c6-104">Example</span></span>  
 <span data-ttu-id="932c6-105">Im folgenden Beispiel werden 5 Zeichen synchron aus einem Array in eine Zeichenfolge geschrieben.</span><span class="sxs-lookup"><span data-stu-id="932c6-105">The following example writes 5 characters synchronously from an array to a string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="932c6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="932c6-106">Example</span></span>  
 <span data-ttu-id="932c6-107">Im nächsten Beispiel werden alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="932c6-107">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="932c6-108">Dann wird jeder Buchstabe bzw. jedes Leerzeichen in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement asynchron gefolgt von einem Zeilenumbruch in eine separate Zeile geschrieben.</span><span class="sxs-lookup"><span data-stu-id="932c6-108">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="932c6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="932c6-109">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="932c6-110">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="932c6-110">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
- [<span data-ttu-id="932c6-111">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="932c6-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [<span data-ttu-id="932c6-112">Gewusst wie: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="932c6-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="932c6-113">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="932c6-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="932c6-114">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="932c6-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="932c6-115">Gewusst wie: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="932c6-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="932c6-116">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="932c6-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="932c6-117">Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="932c6-117">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
