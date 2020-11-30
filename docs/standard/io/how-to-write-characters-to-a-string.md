---
title: 'Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge'
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: 21661a858cff9fc8bc84d497b4af8bedb1393f0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734529"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="71d2e-102">Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="71d2e-102">How to: Write characters to a string</span></span>

<span data-ttu-id="71d2e-103">In den folgenden Codebeispielen werden Zeichen synchron oder asynchron aus einem Zeichenarray in eine Zeichenfolge geschrieben.</span><span class="sxs-lookup"><span data-stu-id="71d2e-103">The following code examples write characters synchronously or asynchronously from a character array into a string.</span></span>  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a><span data-ttu-id="71d2e-104">Beispiel: Synchrones Schreiben von Zeichen in einer Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="71d2e-104">Example: Write characters synchronously in a console app</span></span>  

 <span data-ttu-id="71d2e-105">In dem folgenden Beispiel wird ein <xref:System.IO.StringWriter> verwendet, um fünf Zeichen synchron in ein <xref:System.Text.StringBuilder>-Objekt zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="71d2e-105">The following example uses a <xref:System.IO.StringWriter> to write five characters synchronously to a <xref:System.Text.StringBuilder> object.</span></span>
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a><span data-ttu-id="71d2e-106">Beispiel: Asynchrones Schreiben von Zeichen in einer WPF-App</span><span class="sxs-lookup"><span data-stu-id="71d2e-106">Example: Write characters asynchronously in a WPF app</span></span>

 <span data-ttu-id="71d2e-107">Im nächsten Beispiel wird der Code hinter einer WPF-App gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71d2e-107">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="71d2e-108">Beim Laden des Fensters werden in diesem Beispiel alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="71d2e-108">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="71d2e-109">Dann wird jeder Buchstabe bzw. jedes Leerzeichen asynchron in eine separate Zeile in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement geschrieben.</span><span class="sxs-lookup"><span data-stu-id="71d2e-109">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="71d2e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71d2e-110">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="71d2e-111">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="71d2e-111">File and stream I/O</span></span>](index.md)  
- [<span data-ttu-id="71d2e-112">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="71d2e-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- [<span data-ttu-id="71d2e-113">How to: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="71d2e-113">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="71d2e-114">How to: Lesen von bzw. Schreiben in eine neu erstellte Datendatei</span><span class="sxs-lookup"><span data-stu-id="71d2e-114">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="71d2e-115">How to: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="71d2e-115">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="71d2e-116">How to: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="71d2e-116">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="71d2e-117">How to: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="71d2e-117">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="71d2e-118">How to: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="71d2e-118">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)
