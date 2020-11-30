---
title: 'Vorgehensweise: Lesen von Text aus einer Datei'
description: In diesem Artikel finden Sie Beispiele, wie Text synchron oder asynchron aus einer Textdatei mithilfe der StreamReader-Klasse in .NET für Desktop-Apps gelesen wird.
ms.date: 01/03/2019
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
ms.openlocfilehash: 48b862ff77bf4ace48a5481fe9bedcf354b5654b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725338"
---
# <a name="how-to-read-text-from-a-file"></a>Vorgehensweise: Lesen von Text aus einer Datei

In den folgenden Beispielen wird das synchrone und asynchrone Lesen aus einer Textdatei mithilfe von .NET für Desktop-Apps veranschaulicht. In beiden Beispielen geben Sie beim Erstellen der Instanz der <xref:System.IO.StreamReader>-Klasse einen absoluten oder relativen Pfad zur Datei an.
  
> [!NOTE]
> Diese Codebeispiele gelten nicht für Apps für die Universelle Windows-Plattform (UWP), da die Windows-Runtime verschiedene Streamtypen für Lese- und Schreibvorgänge für Dateien bereitstellt. Ein Beispiel für das Lesen von Text aus einer Datei in einer UWP-App finden Sie unter [Schnellstart: Lesen und Schreiben von Dateien](/previous-versions/windows/apps/hh758325(v=win.10)). Beispiele für die Konvertierung von .NET Framework-Streams in Windows-Runtime-Streams und umgekehrt finden Sie unter [Vorgehensweise: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Beispiel: Synchrones Lesen in einer Konsolen-App  

Im folgenden Beispiel wird ein synchroner Lesevorgang in einer Konsolen-App veranschaulicht. In diesem Beispiel wird die Textdatei mit einem StreamReader geöffnet, ihr Inhalt wird in eine Zeichenfolge kopiert, und die Zeichenfolge wird an die Konsole ausgegeben.  
  
> [!IMPORTANT]
> In dem Beispiel wird angenommen, dass eine Datei mit dem Namen *TestFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/sync-console/Program.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/sync-console/Program.vb":::
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Beispiel: Asynchrones Lesen in einer WPF-App

 Im folgenden Beispiel wird ein asynchroner Lesevorgang in einer WPF-App veranschaulicht.  
  
> [!IMPORTANT]
> In dem Beispiel wird angenommen, dass eine Datei mit dem Namen *TestFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/async-wpf/MainWindow.xaml.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/async-wpf/MainWindow.xaml.vb":::
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [Asynchrone Datei-E/A](asynchronous-file-i-o.md)  
- [How to: Erstellen einer Verzeichnisauflistung](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Schnellstart: Lesen und Schreiben von Dateien](/previous-versions/windows/apps/hh758325(v=win.10))  
- [How to: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [How to: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [How to: Öffnen und Anfügen an eine Protokolldatei](how-to-open-and-append-to-a-log-file.md)  
- [How to: Schreiben von Text in eine Datei](how-to-write-text-to-a-file.md)  
- [How to: Lesen von Zeichen aus einer Zeichenfolge](how-to-read-characters-from-a-string.md)  
- [How to: Schreiben von Zeichen in eine Zeichenfolge](how-to-write-characters-to-a-string.md)  
- [Datei- und Stream-E/A](index.md)
