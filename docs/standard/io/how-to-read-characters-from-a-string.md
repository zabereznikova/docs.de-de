---
title: 'Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c4023d8e801da542414aac1fddaf7aef5bf1e98f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="2acda-102">Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2acda-102">How to: Read Characters from a String</span></span>
<span data-ttu-id="2acda-103">In den folgenden Codebeispielen wird das synchrone und asynchrone Lesen von Zeichen aus einer Zeichenfolge veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2acda-103">The following code examples show how to read characters synchronously and asynchronously from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2acda-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2acda-104">Example</span></span>  
 <span data-ttu-id="2acda-105">In diesem Beispiel werden 13 Zeichen synchron aus einer Zeichenfolge gelesen, in einem Array gespeichert und als Zeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2acda-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays those characters.</span></span> <span data-ttu-id="2acda-106">Anschließend werden die restlichen Zeichen in der Zeichenfolge gelesen und im Array beginnend mit dem sechsten Element gespeichert. Dann wird der Inhalt des Arrays angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2acda-106">It then reads the remaining characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="2acda-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2acda-107">Example</span></span>  
 <span data-ttu-id="2acda-108">Im nächsten Beispiel werden alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2acda-108">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="2acda-109">Dann wird jeder Buchstabe bzw. jedes Leerzeichen in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement asynchron gefolgt von einem Zeilenumbruch in eine separate Zeile geschrieben.</span><span class="sxs-lookup"><span data-stu-id="2acda-109">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2acda-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2acda-110">See Also</span></span>  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2acda-111">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="2acda-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="2acda-112">NIB: Gewusst wie: Erstellen einer Verzeichnisauflistung</span><span class="sxs-lookup"><span data-stu-id="2acda-112">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="2acda-113">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="2acda-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="2acda-114">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="2acda-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="2acda-115">Gewusst wie: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="2acda-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="2acda-116">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="2acda-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="2acda-117">Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2acda-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="2acda-118">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="2acda-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
