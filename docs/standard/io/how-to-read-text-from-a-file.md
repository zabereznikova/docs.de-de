---
title: 'Vorgehensweise: Lesen von Text aus einer Datei'
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
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: 8676e5f0acd0646b4854df7dde060ec15548ec3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155723"
---
# <a name="how-to-read-text-from-a-file"></a>Vorgehensweise: Lesen von Text aus einer Datei
In den folgenden Beispielen wird das synchrone und asynchrone Lesen aus einer Textdatei mithilfe von .NET für Desktop-Apps veranschaulicht. In beiden Beispielen geben Sie beim Erstellen der Instanz der <xref:System.IO.StreamReader>-Klasse einen absoluten oder relativen Pfad zur Datei an.
  
> [!NOTE]
> Diese Codebeispiele gelten nicht für die Entwicklung von Apps für die Universelle Windows-Plattform (UWP), da die Windows-Runtime verschiedene Streamtypen für Lese- und Schreibvorgänge für Dateien bereitstellt. Ein Beispiel für das Lesen von Text aus einer Datei in einer UWP-App finden Sie unter [Schnellstart: Lesen und Schreiben von Dateien](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)). Beispiele für die Konvertierung von .NET Framework-Streams in Windows-Runtime-Streams und umgekehrt finden Sie unter [Vorgehensweise: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Beispiel: Synchrones Lesen in einer Konsolen-App  
Im folgenden Beispiel wird ein synchroner Lesevorgang in einer Konsolen-App veranschaulicht. In diesem Beispiel wird die Textdatei mit einem StreamReader geöffnet, ihr Inhalt wird in eine Zeichenfolge kopiert, und die Zeichenfolge wird an die Konsole ausgegeben.  
  
> [!IMPORTANT]
> In dem Beispiel wird angenommen, dass eine Datei mit dem Namen *TestFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Beispiel: Asynchrones Lesen in einer WPF-App
 Im folgenden Beispiel wird ein asynchroner Lesevorgang in einer WPF-App veranschaulicht.  
  
> [!IMPORTANT]
> In dem Beispiel wird angenommen, dass eine Datei mit dem Namen *TestFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [Asynchrone Datei-E/A](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [How to: Erstellen einer Verzeichnisauflistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Schnellstart: Lesen und Schreiben von Dateien](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [How to: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [How to: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [How to: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [How to: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [How to: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [How to: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
