---
title: 'Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge'
ms.date: 01/21/2019
ms.technology: dotnet-standard
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
ms.openlocfilehash: 0c3516c4abadfd22609c3568beffc14e027ef69e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706672"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="dc508-102">Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="dc508-102">How to: Read characters from a string</span></span>
<span data-ttu-id="dc508-103">In den folgenden Codebeispielen wird das synchrone und asynchrone Lesen von Zeichen aus einer Zeichenfolge veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dc508-103">The following code examples show how to read characters synchronously or asynchronously from a string.</span></span>  
  
## <a name="example-read-characters-synchronously"></a><span data-ttu-id="dc508-104">Beispiel: Synchrones Lesen von Zeichen</span><span class="sxs-lookup"><span data-stu-id="dc508-104">Example: Read characters synchronously</span></span> 
 <span data-ttu-id="dc508-105">In diesem Beispiel werden 13 Zeichen synchron aus einer Zeichenfolge gelesen, in einem Array gespeichert und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc508-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays them.</span></span> <span data-ttu-id="dc508-106">Anschließend werden in dem Beispiel die restlichen Zeichen in der Zeichenfolge gelesen und im Array beginnend mit dem sechsten Element gespeichert. Dann wird der Inhalt des Arrays angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc508-106">The example then reads the rest of the characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a><span data-ttu-id="dc508-107">Beispiel: Asynchrones Lesen von Zeichen</span><span class="sxs-lookup"><span data-stu-id="dc508-107">Example: Read characters asynchronously</span></span>  
 <span data-ttu-id="dc508-108">Im nächsten Beispiel wird der Code hinter einer WPF-App gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc508-108">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="dc508-109">Beim Laden des Fensters werden in diesem Beispiel alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc508-109">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="dc508-110">Dann wird jeder Buchstabe bzw. jedes Leerzeichen asynchron in eine separate Zeile in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc508-110">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dc508-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc508-111">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="dc508-112">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="dc508-112">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- <span data-ttu-id="dc508-113">[Vorgehensweise: Erstellen einer Verzeichnisauflistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dc508-113">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="dc508-114">Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei</span><span class="sxs-lookup"><span data-stu-id="dc508-114">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="dc508-115">Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="dc508-115">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="dc508-116">Vorgehensweise: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="dc508-116">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="dc508-117">Vorgehensweise: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="dc508-117">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="dc508-118">Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="dc508-118">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="dc508-119">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="dc508-119">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
