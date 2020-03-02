---
title: 'Vorgehensweise: Schreiben von Text in eine Datei'
ms.date: 01/04/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: ba1c1815f0e49c02d1f0ee3c48ba01b7c2f5e727
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160247"
---
# <a name="how-to-write-text-to-a-file"></a>Vorgehensweise: Schreiben von Text in eine Datei
In diesem Artikel werden verschiedene Vorgehensweisen zum Schreiben von Text in eine Datei für eine .NET-Anwendung veranschaulicht.

Die folgenden Klassen und Methoden werden in der Regel zum Schreiben von Text in eine Datei verwendet:  
  
- <xref:System.IO.StreamWriter> enthält Methoden zum synchronen (<xref:System.IO.StreamWriter.Write%2A> und <xref:System.IO.TextWriter.WriteLine%2A>) oder asynchronen (<xref:System.IO.StreamWriter.WriteAsync%2A> und <xref:System.IO.StreamWriter.WriteLineAsync%2A>) Schreiben in eine Datei.  
  
- <xref:System.IO.File> stellt statische Methoden zum Schreiben von Text in eine Datei (z. B. <xref:System.IO.File.WriteAllLines%2A> und <xref:System.IO.File.WriteAllText%2A>) oder zum Anfügen von Text an eine Datei (z. B. <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> und <xref:System.IO.File.AppendText%2A>) bereit.  
  
- <xref:System.IO.Path> wird für Zeichenfolgen verwendet, die Informationen zu Datei- oder Verzeichnispfaden enthalten. Diese Klasse enthält die <xref:System.IO.Path.Combine%2A>-Methode und ab .NET Core 2.1 die Methoden <xref:System.IO.Path.Join%2A> und <xref:System.IO.Path.TryJoin%2A>, mit denen die Verkettung von Zeichenfolgen zum Erstellen eines Datei- oder Verzeichnispfads ermöglicht wird.

> [!NOTE]
> In den folgenden Beispielen wird nur das Mindeste des erforderlichen Codes veranschaulicht. Reale Anwendungen umfassen im Allgemeinen eine robustere Fehlerüberprüfung und Ausnahmebehandlung.  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a>Beispiel: Synchrones Schreiben von Text mit StreamWriter

Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.IO.StreamWriter>-Klasse verwenden, um Text zeilenweise synchron in eine neue Datei zu schreiben. Da das <xref:System.IO.StreamWriter>-Objekt in einer `using`-Anweisung deklariert und instanziiert ist, wird die <xref:System.IO.StreamWriter.Dispose%2A>-Methode aufgerufen, die den Datenstrom automatisch leert und beendet.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a>Beispiel: Synchrones Anfügen von Text mit StreamWriter

Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.IO.StreamWriter>-Klasse verwenden, um Text synchron an die Textdatei anzufügen, die im ersten Beispiel erstellt wurde.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a>Beispiel: Asynchrones Schreiben von Text mit StreamWriter

Das folgende Beispiel zeigt, wie Sie Text mithilfe der <xref:System.IO.StreamWriter> -Klasse asynchron in eine neue Datei schreiben. Der Methodenaufruf muss sich innerhalb einer `async`-Methode befinden, um die <xref:System.IO.StreamWriter.WriteAsync%2A>-Methode aufzurufen. Für das C#-Beispiel ist C# 7.1 oder höher erforderlich, da der Programmeinstiegspunkt den `async`-Modifizierer unterstützt.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a>Beispiel: Schreiben und Anfügen von Text mit der File-Klasse

Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.File> -Klasse Text in eine neue Datei schreiben und neue Textzeilen an diese Datei anfügen. Durch die Methoden <xref:System.IO.File.WriteAllText%2A> und <xref:System.IO.File.AppendAllLines%2A> wird die Datei automatisch geöffnet und geschlossen. Wenn der für die <xref:System.IO.File.WriteAllText%2A> -Methode angegebene Pfad bereits vorhanden ist, wird die Datei überschrieben.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [How to: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [How to: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [How to: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [How to: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
