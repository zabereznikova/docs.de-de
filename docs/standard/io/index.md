---
title: Datei- und Stream-E/A – .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- IO namespace
- files, I/O
- System.IO namespace
- I/O [.NET Framework]
- streams, I/O
- data streams, I/O
ms.assetid: 4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2
ms.openlocfilehash: 3c69e0fd23b1f8bc11fe908c66ba492f31a53f30
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706594"
---
# <a name="file-and-stream-io"></a>Datei- und Stream-E/A

Datei- und Stream-E/A (Eingabe/Ausgabe) bezieht sich auf die Übertragung von Daten auf ein oder von einem Speichermedium. Im .NET Framework enthalten die `System.IO`-Namespaces Typen, die das synchrone und asynchrone Lesen und Schreiben in Datenströmen und Dateien ermöglichen. Diese Namespaces enthalten zudem Typen für die Komprimierung und Dekomprimierung von Dateien sowie Typen für die Kommunikation über Pipes und serielle Anschlüsse.

Eine Datei ist eine geordnete, mit einem Namen versehene Auflistung von dauerhaft gespeicherten Bytes. Beim Umgang mit Dateien arbeiten Sie mit Verzeichnispfaden, Datenträgern sowie mit Datei- und Verzeichnisnamen. Im Unterschied dazu, handelt es sich bei einem Stream um eine Sequenz von Bytes, die zum Lesen von und zum Schreiben in einen Sicherungsspeicher verwendet wird, für den unterschiedliche Speichermedien (z. B. Festplatten oder Arbeitsspeicher) verwendet werden können. Ebenso wie es neben Festplatten mehrere andere Sicherungsspeicher gibt, gibt es neben Dateistreams zusätzlich Netzwerk-, Speicher- und Pipestreams.

## <a name="files-and-directories"></a>Dateien und Verzeichnisse

Sie können die Typen im <xref:System.IO?displayProperty=nameWithType>-Namespace verwenden, um mit Dateien und Verzeichnissen zu interagieren. Beispielsweise können Sie Eigenschaften für Dateien und Verzeichnisse abrufen und festlegen oder Auflistungen von Dateien und Verzeichnissen anhand von Suchkriterien abrufen.

Informationen zu Dateibenennungskonventionen und wie Sie einen Dateipfad für Windows-Systeme formulieren können (z.B. die DOS-Gerätesyntax, die in .NET Core 1.1 und höher und in .NET Framework 4.6.2 und höher unterstützt wird) finden Sie unter [File path formats on Windows systems (Dateipfadformate unter Windows-Systemen)](file-path-formats.md).

Im Folgenden sind einige häufig verwendete Datei- und Verzeichnisklassen aufgeführt:

- <xref:System.IO.File> – stellt statische Methoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines <xref:System.IO.FileStream>-Objekts.

- <xref:System.IO.FileInfo> – stellt Instanzmethoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines <xref:System.IO.FileStream>-Objekts.

- <xref:System.IO.Directory> – stellt statische Methoden zum Erstellen, Verschieben und Auflisten von Verzeichnissen und Unterverzeichnissen zur Verfügung.

- <xref:System.IO.DirectoryInfo> – stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten von Verzeichnissen und Unterverzeichnissen zur Verfügung.

- <xref:System.IO.Path> – stellt Methoden und Eigenschaften für die plattformübergreifende Verarbeitung von Verzeichniszeichenfolgen zur Verfügung.

Beim Aufrufen von Methoden des Dateisystems sollten Sie immer eine robuste Ausnahmebehandlung zur Verfügung stellen. Weitere Informationen hierzu finden Sie unter [Behandeln von E/A-Fehlern](handling-io-errors.md).

Neben der Verwendung dieser Klassen können Benutzer von Visual Basic die von der <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=nameWithType>-Klasse für Datei-E/A-Vorgänge bereitgestellten Methoden und Eigenschaften verwenden.

Weitere Informationen finden Sie unter [How to: Kopieren von Verzeichnissen](how-to-copy-directories.md), [Vorgehensweise: Erstellen einer Verzeichnisauflistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100)) und [Vorgehensweise: Auflisten von Verzeichnissen und Dateien](how-to-enumerate-directories-and-files.md).

## <a name="streams"></a>Streams

Die abstrakte <xref:System.IO.Stream>-Basisklasse unterstützt das Lesen und Schreiben von Bytes. Alle Klassen, die Streams darstellen, erben von der <xref:System.IO.Stream>-Klasse. Die <xref:System.IO.Stream>-Klasse und die davon abgeleiteten Klassen stellen eine allgemeine Ansicht von Datenquellen und Repositorys bereit, sodass Programmierer sich nicht mit den Einzelheiten des Betriebssystems und der jeweiligen Geräte befassen müssen.

Streams umfassen drei grundlegende Vorgänge:

- Lesen – Übertragen der Daten von einem Stream in eine Datenstruktur, beispielsweise in ein Bytearray.

- Schreiben – Übertragen von Daten aus einer Datenquelle in einen Stream.

- Suchen – Abfragen und bearbeiten der aktuellen Position innerhalb eines Streams.

Abhängig von der zugrunde liegenden Datenquelle oder vom Repository unterstützt ein Stream möglicherweise nur einige dieser Funktionen. Die <xref:System.IO.Pipes.PipeStream>-Klasse unterstützt beispielsweise keine Suchvorgänge. Die <xref:System.IO.Stream.CanRead%2A>-, <xref:System.IO.Stream.CanWrite%2A>- und <xref:System.IO.Stream.CanSeek%2A>-Eigenschaften eines Stream geben die Vorgänge an, die vom Stream unterstützt werden.

Im Folgenden sind einige häufig verwendete Streamklassen aufgeführt:

- <xref:System.IO.FileStream> – Lesen und Schreiben in einer Datei.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> – Lesen und Schreiben in einer Datei im isolierten Speicher.

- <xref:System.IO.MemoryStream> – Lesen und Schreiben im Arbeitsspeicher als Sicherungsspeicher.

- <xref:System.IO.BufferedStream> – Verbessern der Leistung von Lese- und Schreibvorgängen.

- <xref:System.Net.Sockets.NetworkStream> – Lesen und Schreiben über Netzwerksockets.

- <xref:System.IO.Pipes.PipeStream> – Lesen und Schreiben über anonyme und benannte Pipes.

- <xref:System.Security.Cryptography.CryptoStream> – Verknüpfen von Datenstreams mit kryptografischen Transformationen.

Ein Beispiel für asynchrones Arbeiten mit Streams finden Sie unter [Asynchrone Datei-E/A](asynchronous-file-i-o.md).

## <a name="readers-and-writers"></a>Reader und Writer

Der <xref:System.IO?displayProperty=nameWithType>-Namespace stellt zudem Typen zum Lesen und Schreiben von codierten Zeichen in Streams bereit. Normalerweise werden Streams für die Eingabe und Ausgabe von Bytes verwendet. Die Reader- und Writer-Typen übernehmen die Konvertierung der codierten Zeichen in Bytes und umgekehrt, sodass der Vorgang im Stream abgeschlossen werden kann. Jede Reader- und Writer-Klasse ist einem Stream zugeordnet, der durch die `BaseStream`-Eigenschaft der Klasse abgerufen werden kann.

Im Folgenden werden einige häufig verwendete Reader- und Writer-Klassen aufgeführt:

- <xref:System.IO.BinaryReader> und <xref:System.IO.BinaryWriter> – Lesen und Schreiben von primitiven Datentypen als Binärwerte.

- <xref:System.IO.StreamReader> und <xref:System.IO.StreamWriter> – Lesen und Schreiben von Zeichen mithilfe eines Codierungswerts, der die Zeichen in Bytes konvertiert und umgekehrt.

- <xref:System.IO.StringReader> und <xref:System.IO.StringWriter> -– Lesen und Schreiben von Zeichen in und aus Zeichenfolgen.

- <xref:System.IO.TextReader> und <xref:System.IO.TextWriter> – abstrakte Basisklassen für andere Reader und Writer, die Zeichen und Zeichenfolgen, jedoch keine Binärdaten, lesen und schreiben.

Weitere Informationen finden Sie unter [How to: Lesen aus einer Textdatei](how-to-read-text-from-a-file.md), [Vorgehensweise: Schreiben von Text in eine Datei](how-to-write-text-to-a-file.md), [Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge](how-to-read-characters-from-a-string.md) und [Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge](how-to-write-characters-to-a-string.md).

## <a name="asynchronous-io-operations"></a>Asynchrone E/A-Vorgänge

Das Lesen oder Schreiben einer großen Datenmenge kann ressourcenintensiv sein. Damit Ihre Anwendung weiterhin auf Benutzerinteraktionen reagiert, sollten Sie diese Aufgaben asynchron ausführen. Bei synchronen E/A-Vorgängen wird der UI-Thread blockiert, bis der ressourcenintensive Vorgang abgeschlossen ist.  Verwenden Sie beim Entwickeln von Windows Store-Apps Version 8.x asynchrone E/A-Vorgänge, damit nicht der Eindruck erweckt wird, dass Ihre App nicht mehr reagiert.

Die asynchronen Member enthalten den Begriff `Async` in ihren Namen, z. B. die Methoden <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>,  <xref:System.IO.Stream.ReadAsync%2A> und <xref:System.IO.Stream.WriteAsync%2A>. Diese Methoden müssen mit den Schlüsselwörtern `async` und `await` verwendet werden.

Weitere Informationen finden Sie unter [Asynchrone Datei-E/A](asynchronous-file-i-o.md).

## <a name="compression"></a>Komprimierung

Komprimierung bezieht sich auf das Verkleinern einer Datei zum Zweck der Speicherung. Bei einer Dekomprimierung wird der Inhalt einer komprimierten Datei extrahiert und in ein verwendbares Format gebracht. Der <xref:System.IO.Compression?displayProperty=nameWithType>-Namespace enthält Typen zum Komprimieren und Dekomprimieren von Dateien und Streams.

Die folgenden Klassen werden häufig zum Komprimieren und Dekomprimieren von Dateien und Streams verwendet:

- <xref:System.IO.Compression.ZipArchive> – Erstellen und Abrufen von Einträgen im ZIP-Archiv.

- <xref:System.IO.Compression.ZipArchiveEntry> – Darstellen einer komprimierten Datei.

- <xref:System.IO.Compression.ZipFile> – Erstellen, Extrahieren und Öffnen eines komprimierten Pakets.

- <xref:System.IO.Compression.ZipFileExtensions> – Erstellen und Extrahieren von Einträgen in einem komprimierten Paket.

- <xref:System.IO.Compression.DeflateStream> – Komprimieren und Dekomprimieren von Streams mit dem Deflate-Algorithmus.

- <xref:System.IO.Compression.GZipStream> – Komprimieren und Dekomprimieren von Streams im gzip-Datenformat.

Weitere Informationen finden Sie unter [How to: Komprimieren und Extrahieren von Dateien](how-to-compress-and-extract-files.md).

## <a name="isolated-storage"></a>Isolierter Speicher

Isolierte Speicherung ist ein Mechanismus zur Datenspeicherung, der Isolation und Sicherheit gewährleistet. Dies wird durch die Definition standardisierter Verknüpfungen von Code mit gespeicherten Daten ermöglicht. Der Speicher enthält ein virtuelles Dateisystem, das nach Benutzer, Assembly und Domäne (optional) isoliert ist. Ein isolierter Speicher ist besonders nützlich, wenn Ihre Anwendung keine Berechtigung für den Zugriff auf Benutzerdateien hat. Sie können die Einstellungen oder Dateien für die Anwendung so speichern, dass eine Kontrolle durch die Sicherheitsrichtlinien des Computers gewährleistet ist.

Isolierter Speicher ist für Windows Store-Apps Version 8.x nicht verfügbar. Verwenden Sie stattdessen Anwendungsdatenklassen im <xref:Windows.Storage?displayProperty=nameWithType>-Namespace. Weitere Informationen finden Sie unter [Anwendungsdaten](https://docs.microsoft.com/previous-versions/windows/apps/hh464917%28v=win.10%29).

Die folgenden Klassen werden häufig zum Implementieren isolierter Speicher verwendet:

- <xref:System.IO.IsolatedStorage.IsolatedStorage> – stellt die Basisklasse für Implementierungen isolierter Speicher bereit.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile> – stellt einen Bereich des isolierten Speichers mit Dateien und Verzeichnissen bereit.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> – macht eine Datei im isolierten Speicher verfügbar.

Weitere Informationen finden Sie unter [Isolierter Speicher](isolated-storage.md).

## <a name="io-operations-in-windows-store-apps"></a>E/A-Vorgänge in Windows Store-Apps

Die .NET für Windows 8.x Store-Apps enthalten viele der Typen zum Lesen und Schreiben in Streams. Jedoch sind nicht alle E/A-Typen von .NET Framework verfügbar.

Beachten Sie jedoch die folgenden wichtigen Unterschiede, wenn Sie E/A-Vorgänge in Windows Store-Apps Version 8.x verwenden:

- Typen, mit speziellem Bezug auf Dateivorgänge, z. B. <xref:System.IO.File>, <xref:System.IO.FileInfo>, <xref:System.IO.Directory> und <xref:System.IO.DirectoryInfo>, sind in den .NET für Windows 8.x Store-Apps nicht enthalten. Verwenden Sie stattdessen die Typen im <xref:Windows.Storage?displayProperty=nameWithType>-Namespace der Windows-Runtime, wie z.B. <xref:Windows.Storage.StorageFile> und <xref:Windows.Storage.StorageFolder>.

- Die isolierte Speicherung ist nicht verfügbar. Verwenden Sie stattdessen [Anwendungsdaten](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10)).

- Verwenden Sie asynchrone Methoden, wie <xref:System.IO.Stream.ReadAsync%2A> und <xref:System.IO.Stream.WriteAsync%2A>, um zu verhindern, dass UI-Threads blockiert werden.

- Die auf einem Pfad basierenden Komprimierungstypen <xref:System.IO.Compression.ZipFile> und <xref:System.IO.Compression.ZipFileExtensions> sind nicht verfügbar. Verwenden Sie stattdessen die Typen im <xref:Windows.Storage.Compression?displayProperty=nameWithType>-Namespace.

Sie können .NET Framework-Streams in Windows-Runtime-Streams konvertieren und umgekehrt, falls erforderlich. Weitere Informationen finden Sie unter [Vorgehensweise: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](how-to-convert-between-dotnet-streams-and-winrt-streams.md) oder unter <xref:System.IO.WindowsRuntimeStreamExtensions>.

Weitere Informationen zu E/A-Vorgängen in einer Windows Store-App Version 8.x finden Sie unter [Schnellstart: Lesen und Schreiben von Dateien](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).

## <a name="io-and-security"></a>E/A und Sicherheit

Wenn Sie die Klassen im <xref:System.IO?displayProperty=nameWithType>-Namespace verwenden, müssen die Sicherheitsanforderungen des Betriebssystems erfüllt sein, z. B. Zugriffssteuerungslisten (ACLs), um den Zugriff auf Dateien und Verzeichnisse zu steuern. Dies gilt zusätzlich zu anderen <xref:System.Security.Permissions.FileIOPermission>-Anforderungen. ACLs können programmgesteuert verwaltet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen](how-to-add-or-remove-access-control-list-entries.md).

Standardsicherheitsrichtlinien verhindern den Zugriff von Internet- oder Intranetanwendungen auf Dateien, die sich auf dem Computer des Benutzers befinden. Verwenden Sie daher beim Schreiben von Code, der über das Internet oder Intranet heruntergeladen wird, keine E/A-Klassen, für die ein Pfad zu einer physischen Datei erforderlich ist. Verwenden Sie stattdessen [isolierte Speicherung](isolated-storage.md) für herkömmliche .NET Framework-Anwendungen oder [Anwendungsdaten](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10)) für Windows Store-Apps Version 8.x.

Eine Sicherheitsüberprüfung wird nur beim Erstellen des Streams ausgeführt. Übergeben Sie daher keinen geöffneten Stream an weniger vertrauenswürdigen Code oder an Anwendungsdomänen.

## <a name="related-topics"></a>Verwandte Themen

- [Allgemeine E/A-Tasks](common-i-o-tasks.md)\
Stellt eine Liste von E/A-Aufgaben bereit, die Dateien, Verzeichnissen und Streams zugeordnet sind, und verknüpft jede Aufgabe mit relevanten Inhalten und Beispielen.

- [Asynchrone Datei-E/A](asynchronous-file-i-o.md)\
Beschreibt die Leistungsvorteile und den grundlegenden Ablauf der asynchronen E/A.

- [Isolierter Speicher](isolated-storage.md)\
Beschreibt einen Mechanismus zur Datenspeicherung, der durch Definition einer standardisierten Zuordnung von Code zu gespeicherten Daten Isolierung und Sicherheit gewährleistet.

- [Pipes](pipe-operations.md)\
Beschreibt anonyme und benannte Pipevorgänge im .NET Framework.

- [Speicherabbilddateien](memory-mapped-files.md)\
Beschreibt Speicherabbilddateien, die den Inhalt von Dateien auf dem Datenträger im virtuellen Arbeitsspeicher enthalten. Sie können Speicherabbilddateien verwenden, um sehr große Dateien zu bearbeiten und gemeinsam genutzten Speicherbereich für die prozessübergreifende Kommunikation zu erstellen.
