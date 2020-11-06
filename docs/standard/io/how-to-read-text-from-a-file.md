---
title: 'Vorgehensweise: Lesen von Text aus einer Datei'
description: In diesem Artikel finden Sie Beispiele, wie Text synchron oder asynchron aus einer Textdatei mithilfe der StreamReader-Klasse in .NET für Desktop-Apps gelesen wird.
ms.date: 01/03/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: 0e90887c2cc4a54355c51facf91c9cc3da7e4320
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189328"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="a2a32-103">Vorgehensweise: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="a2a32-103">How to: Read text from a file</span></span>

<span data-ttu-id="a2a32-104">In den folgenden Beispielen wird das synchrone und asynchrone Lesen aus einer Textdatei mithilfe von .NET für Desktop-Apps veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a2a32-104">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="a2a32-105">In beiden Beispielen geben Sie beim Erstellen der Instanz der <xref:System.IO.StreamReader>-Klasse einen absoluten oder relativen Pfad zur Datei an.</span><span class="sxs-lookup"><span data-stu-id="a2a32-105">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2a32-106">Diese Codebeispiele gelten nicht für Apps für die Universelle Windows-Plattform (UWP), da die Windows-Runtime verschiedene Streamtypen für Lese- und Schreibvorgänge für Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a2a32-106">These code examples do not apply to Universal Windows (UWP) apps, because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="a2a32-107">Ein Beispiel für das Lesen von Text aus einer Datei in einer UWP-App finden Sie unter [Schnellstart: Lesen und Schreiben von Dateien](/previous-versions/windows/apps/hh758325(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="a2a32-107">For an example that shows how to read text from a file in a UWP app, see [Quickstart: Reading and writing files](/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="a2a32-108">Beispiele für die Konvertierung von .NET Framework-Streams in Windows-Runtime-Streams und umgekehrt finden Sie unter [Vorgehensweise: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="a2a32-108">For examples that show how to convert between .NET Framework streams and Windows Runtime streams, see [How to: Convert between .NET Framework streams and Windows Runtime streams](how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example-synchronous-read-in-a-console-app"></a><span data-ttu-id="a2a32-109">Beispiel: Synchrones Lesen in einer Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="a2a32-109">Example: Synchronous read in a console app</span></span>  
<span data-ttu-id="a2a32-110">Im folgenden Beispiel wird ein synchroner Lesevorgang in einer Konsolen-App veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a2a32-110">The following example shows a synchronous read operation within a console app.</span></span> <span data-ttu-id="a2a32-111">In diesem Beispiel wird die Textdatei mit einem StreamReader geöffnet, ihr Inhalt wird in eine Zeichenfolge kopiert, und die Zeichenfolge wird an die Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a2a32-111">This example opens the text file using a stream reader, copies the contents to a string, and outputs the string to the console.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a2a32-112">In dem Beispiel wird angenommen, dass eine Datei mit dem Namen *TestFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.</span><span class="sxs-lookup"><span data-stu-id="a2a32-112">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/sync-console/Program.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/sync-console/Program.vb":::
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a><span data-ttu-id="a2a32-113">Beispiel: Asynchrones Lesen in einer WPF-App</span><span class="sxs-lookup"><span data-stu-id="a2a32-113">Example: Asynchronous read in a WPF app</span></span>
 <span data-ttu-id="a2a32-114">Im folgenden Beispiel wird ein asynchroner Lesevorgang in einer WPF-App veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a2a32-114">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) app.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a2a32-115">In dem Beispiel wird angenommen, dass eine Datei mit dem Namen *TestFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.</span><span class="sxs-lookup"><span data-stu-id="a2a32-115">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/async-wpf/MainWindow.xaml.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/async-wpf/MainWindow.xaml.vb":::
  
## <a name="see-also"></a><span data-ttu-id="a2a32-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a32-116">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="a2a32-117">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="a2a32-117">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- <span data-ttu-id="a2a32-118">[How to: Erstellen einer Verzeichnisauflistung](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a2a32-118">[How to: Create a directory listing](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- <span data-ttu-id="a2a32-119">[Schnellstart: Lesen und Schreiben von Dateien](/previous-versions/windows/apps/hh758325(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="a2a32-119">[Quickstart: Reading and writing files](/previous-versions/windows/apps/hh758325(v=win.10))</span></span>  
- [<span data-ttu-id="a2a32-120">How to: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams</span><span class="sxs-lookup"><span data-stu-id="a2a32-120">How to: Convert between .NET Framework streams and Windows Runtime streams</span></span>](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [<span data-ttu-id="a2a32-121">How to: Lesen von bzw. Schreiben in eine neu erstellte Datendatei</span><span class="sxs-lookup"><span data-stu-id="a2a32-121">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="a2a32-122">How to: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="a2a32-122">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="a2a32-123">How to: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="a2a32-123">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="a2a32-124">How to: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2a32-124">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="a2a32-125">How to: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2a32-125">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="a2a32-126">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="a2a32-126">File and stream I/O</span></span>](index.md)
