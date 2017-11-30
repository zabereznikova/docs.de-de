---
title: 'Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9116ec63bfc1d12daf7627186a52bd29d5918485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="20aff-102">Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="20aff-102">How to: Read Characters from a String</span></span>
<span data-ttu-id="20aff-103">Die folgenden Codebeispiele zeigen, wie Zeichen aus einer Zeichenfolge synchron und asynchron zu lesen.</span><span class="sxs-lookup"><span data-stu-id="20aff-103">The following code examples show how to read characters synchronously and asynchronously from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20aff-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20aff-104">Example</span></span>  
 <span data-ttu-id="20aff-105">In diesem Beispiel liest 13 Zeichen belegen synchron aus einer Zeichenfolge in einem Array gespeichert, und zeigt diese Zeichen.</span><span class="sxs-lookup"><span data-stu-id="20aff-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays those characters.</span></span> <span data-ttu-id="20aff-106">Anschließend er liest die restlichen Zeichen in der Zeichenfolge, speichert sie in das Array, beginnend bei dem sechste Element und zeigt den Inhalt des Arrays.</span><span class="sxs-lookup"><span data-stu-id="20aff-106">It then reads the remaining characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="20aff-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20aff-107">Example</span></span>  
 <span data-ttu-id="20aff-108">Im nächste Beispiel liest alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox> steuern und speichert diese in einem Array.</span><span class="sxs-lookup"><span data-stu-id="20aff-108">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="20aff-109">Es asynchron schreibt dann jedes Zeichen Buchstabe oder ein Leerzeichen in einer eigenen Zeile, gefolgt von einem Zeilenumbruch, einem <xref:System.Windows.Controls.TextBlock> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="20aff-109">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="20aff-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20aff-110">See Also</span></span>  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="20aff-111">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="20aff-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="20aff-112">NIB: Vorgehensweise: Erstellen einer Verzeichnisauflistung</span><span class="sxs-lookup"><span data-stu-id="20aff-112">NIB: How to: Create a Directory Listing</span></span>](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="20aff-113">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="20aff-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="20aff-114">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="20aff-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="20aff-115">Gewusst wie: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="20aff-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="20aff-116">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="20aff-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="20aff-117">Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="20aff-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="20aff-118">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="20aff-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
