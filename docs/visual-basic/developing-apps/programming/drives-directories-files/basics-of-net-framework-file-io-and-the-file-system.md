---
title: Grundlagen zu Datei-E/A-Vorgängen und dem Dateisystem in .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- file access, file I/O in Visual Basic
- file attributes, determining
- streams, fundamental operations
- file permissions
- streams
- streams, definition
ms.assetid: 49d837c0-cf28-416f-8606-4d83d7b479ef
ms.openlocfilehash: 5d60d0089d042c0be343c741c26de0b4b7778d6d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348934"
---
# <a name="basics-of-net-framework-file-io-and-the-file-system-visual-basic"></a>Grundlagen zu Datei-E/A-Vorgängen und dem Dateisystem in .NET Framework (Visual Basic)

Klassen im <xref:System.IO>-Namespace werden zum Arbeiten mit Laufwerken, Dateien und Verzeichnissen verwendet.

Der <xref:System.IO>-Namespace enthält die Klassen <xref:System.IO.File> und <xref:System.IO.Directory>, mit denen die Funktionalität von .NET Framework zum Ändern von Dateien und Verzeichnissen bereitgestellt wird. Da die Methoden dieser Objekte statische oder freigegebene Member sind, können Sie diese direkt verwenden, ohne zuerst eine Instanz der Klasse erstellen zu müssen. Die Klassen <xref:System.IO.FileInfo> und <xref:System.IO.DirectoryInfo> werden diesen Klassen zugeordnet und sind den Benutzern der `My`-Funktion bekannt. Zum Verwenden dieser Klassen müssen Sie die Namen vollständig qualifizieren oder die entsprechenden Namespaces durch Einschließen des `Imports` -Arguments (bzw. der Argumente) am Anfang des betreffenden Codes importieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).

> [!NOTE]
> Weitere Themen in diesem Abschnitt verwenden das Objekt `My.Computer.FileSystem` anstelle der `System.IO` -Klassen zum Arbeiten mit Laufwerken, Dateien und Verzeichnissen. Das Objekt `My.Computer.FileSystem` dient in erster Linie zur Verwendung in Visual Basic-Programmen. `System.IO`-Klassen sind für die Verwendung durch eine beliebige Sprache vorgesehen, die .NET Framework, einschließlich Visual Basic, unterstützen.

## <a name="definition-of-a-stream"></a>Definition eines Streams

.NET Framework verwendet Streams, um das Lesen von und Schreiben in Dateien zu unterstützen. Sie können sich einen Stream als eindimensionalen Satz von zusammenhängenden Daten mit einem Anfang und einem Ende vorstellen, bei dem der Cursor die derzeitige Position im Stream anzeigt.

![Cursor markiert die aktuelle Position im Dateistream.](./media/basics-of-net-framework-file-io-and-the-file-system/filestream-cursor-position.gif)

## <a name="stream-operations"></a>Streamoperationen

Die im Stream enthaltenen Daten stammen möglicherweise aus dem Arbeitsspeicher, einer Datei oder einem TCP/IP-Socket. Streams verfügen über grundlegende Operationen, die auf sie angewendet werden können.

- **Lesen**. Sie können aus einem Stream lesen und Daten vom Stream in eine Datenstruktur übertragen, z.B. eine Zeichenfolge oder ein Bytearray.

- **Schreiben**. Sie können in einen Stream schreiben und Daten aus einer Datenquelle in den Stream übertragen.

- **Suchen**. Sie können Ihre Position im Stream abfragen und ändern.

Weitere Informationen finden Sie unter [Composing Streams](../../../../standard/io/composing-streams.md).

## <a name="types-of-streams"></a>Arten von Streams

In .NET Framework wird ein Stream von der <xref:System.IO.Stream>-Klasse dargestellt, die die abstrakte Klasse für alle anderen Streams bildet. Sie können nicht direkt eine Instanz der <xref:System.IO.Stream>-Klasse erstellen, doch Sie müssen eine der Klassen verwenden, die diese implementiert.

Es existieren viele Arten von Streams, doch für die Arbeit mit Dateieingabe und-ausgabe sind die wichtigsten Typen die <xref:System.IO.FileStream>-Klasse, die eine Möglichkeit bietet, aus Dateien zu lesen und in diese zu schreiben sowie die <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>-Klasse, die die Möglichkeit bietet, Dateien und Verzeichnisse in einem isolierten Speicher zu erstellen. Andere Streams, die für die Arbeit mit Dateieingabe und -ausgabe verwendet werden können, sind:

- <xref:System.IO.BufferedStream>

- <xref:System.Security.Cryptography.CryptoStream>

- <xref:System.IO.MemoryStream>

- <xref:System.Net.Sockets.NetworkStream>.

In der nachstehenden Tabelle werden Aufgaben aufgeführt, die häufig mit einem Stream durchgeführt werden:

|Beschreibung|Informationen|
|---|---|
|Lesen und Schreiben in einer Datendatei|[Vorgehensweise: Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](../../../../standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|
|Lesen von Text aus einer Datei|[Vorgehensweise: Lesen von Text aus einer Datei](../../../../standard/io/how-to-read-text-from-a-file.md)|
|Schreiben von Text in eine Datei|[Vorgehensweise: Schreiben von Text in eine Datei](../../../../standard/io/how-to-write-text-to-a-file.md)|
|Lesen von Zeichen aus einer Zeichenfolge|[Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge](../../../../standard/io/how-to-read-characters-from-a-string.md)|
|Schreiben von Zeichen in eine Zeichenfolge|[Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge](../../../../standard/io/how-to-write-characters-to-a-string.md)|
|Verschlüsseln von Daten|[Verschlüsseln von Daten](../../../../standard/security/encrypting-data.md)|
|Entschlüsseln von Daten|[Entschlüsseln von Daten](../../../../standard/security/decrypting-data.md)|

## <a name="file-access-and-attributes"></a>Dateizugriff und Dateiattribute

Sie können steuern, wie Dateien erstellt, geöffnet und mit den Enumerationen <xref:System.IO.FileAccess>, <xref:System.IO.FileMode> und <xref:System.IO.FileShare> freigegeben werden, die die von den Konstruktoren der <xref:System.IO.FileStream>-Klasse verwendeten Flags enthalten. Wenn Sie z.B. einen neuen <xref:System.IO.FileStream> öffnen oder erstellen, lässt die <xref:System.IO.FileMode>-Enumeration zu, dass Sie angeben, ob die Datei zum Anfügen geöffnet ist, ob eine neue Datei erstellt wird, falls die angegebene Datei nicht vorhanden ist, ob die Datei überschrieben wird usw.

Die <xref:System.IO.FileAttributes>-Enumeration ermöglicht das Sammeln von dateispezifischen Informationen. Die <xref:System.IO.FileAttributes>-Enumeration gibt die gespeicherten Attribute der Datei zurück, z.B. ob sie komprimiert, verschlüsselt, ausgeblendet, schreibgeschützt, ein Archiv, ein Verzeichnis, eine Systemdatei oder eine temporäre Datei ist.

In der folgenden Tabelle sind die Tasks bezüglich Dateizugriff und Dateiattributen aufgelistet.

|Beschreibung|Siehe|
|---|---|
|Öffnen und Anfügen an eine Protokolldatei|[Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei](../../../../standard/io/how-to-open-and-append-to-a-log-file.md)|
|Festlegen der Attribute einer Datei|<xref:System.IO.FileAttributes>|

## <a name="file-permissions"></a>Dateiberechtigungen

Die Steuerung des Zugriffs auf Dateien und Verzeichnisse kann mit der <xref:System.Security.Permissions.FileIOPermission>-Klasse vorgenommen werden. Dies kann möglicherweise besonders wichtig für Entwickler mit Web Forms sein, die standardmäßig im Kontext eines bestimmten lokalen Benutzerkontos namens ASPNET ausgeführt werden, das im Rahmen der ASP.NET- und .NET Framework-Installation erstellt wird. Wenn solch eine Anwendung den Zugriff auf eine Ressource anfordert, verfügt das ASPNET-Benutzerkonto über eingeschränkte Berechtigungen, was dazu führen kann, dass der Benutzer an der Ausführung von Aktionen, z.B. dem Schreiben in eine Datei über eine Webanwendung, gehindert wird. Weitere Informationen finden Sie unter <xref:System.Security.Permissions.FileIOPermission>.

## <a name="isolated-file-storage"></a>Isolierte Dateispeicherung

Die isolierte Speicherung versucht die Probleme zu lösen, die bei der Arbeit mit Dateien auftreten, wenn der Benutzer oder der Code nicht die notwendigen Berechtigungen aufweist. Die isolierte Speicherung weist jedem Benutzer ein Datendepot zu, das einen oder mehrere Speicher enthalten kann. Speicher können voneinander nach Benutzer und Assembly isoliert werden. Nur der Benutzer oder die Assembly, der bzw. die einen Speicher erstellt hat, verfügt über Zugriff auf ihn. Ein Speicher verhält sich wie ein vollständiges virtuelles Dateisystem. Sie können innerhalb eines Speichers Verzeichnisse und Dateien erstellen und bearbeiten.

In der nachstehenden Tabelle werden die Aufgaben aufgelistet, die häufig dem isolierten Datenspeicher zugeordnet sind.

|Beschreibung|Siehe|
|---|---|
|Erstellen eines isolierten Speichers|[Vorgehensweise: Erhalten von Speichern für isolierten Speicher](../../../../standard/io/how-to-obtain-stores-for-isolated-storage.md)|
|Auflisten von isolierten Speichern|[Vorgehensweise: Auflisten von Speichern für isolierten Speicher](../../../../standard/io/how-to-enumerate-stores-for-isolated-storage.md)|
|Löschen eines isolierten Speichers|[Vorgehensweise: Löschen von Speichern im isolierten Speicher](../../../../standard/io/how-to-delete-stores-in-isolated-storage.md)|
|Erstellen einer Datei oder eines Verzeichnisses im isolierten Speicher|[Vorgehensweise: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher](../../../../standard/io/how-to-create-files-and-directories-in-isolated-storage.md)|
|Suchen einer Datei im isolierten Speicher|[Vorgehensweise: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher](../../../../standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md)|
|Lesen aus oder Schreiben in einer Datei im isolierten Speicher|[Vorgehensweise: Lesen von bzw. Schreiben in Dateien im isolierten Speicher](../../../../standard/io/how-to-read-and-write-to-files-in-isolated-storage.md)|
|Löschen einer Datei oder eines Verzeichnisses im isolierten Speicher|[Vorgehensweise: Löschen von Dateien und Verzeichnissen in isoliertem Speicher](../../../../standard/io/how-to-delete-files-and-directories-in-isolated-storage.md)|

## <a name="file-events"></a>Dateiereignisse

Mit der Komponente von <xref:System.IO.FileSystemWatcher> können Sie Änderungen in Dateien und Verzeichnissen in Ihrem System oder auf jedem beliebigen Computer, auf dem Sie über Netzwerkzugriff verfügen, überwachen. Wenn z.B. eine Datei verändert wird, möchten Sie möglicherweise eine Warnung an einen Benutzer versenden, dass die Änderung durchgeführt wurde. Wenn Änderungen auftreten, werden ein Ereignis oder mehrere Ereignisse ausgelöst, in einem Puffer gespeichert und an die <xref:System.IO.FileSystemWatcher>-Komponente für die Verarbeitung übermittelt.

## <a name="see-also"></a>Siehe auch

- [Erstellen von Streams](../../../../standard/io/composing-streams.md)
- [Datei- und Stream-E/A](../../../../standard/io/index.md)
- [Asynchronous File I/O](../../../../standard/io/asynchronous-file-i-o.md)
- [Für Datei-E/A-Vorgänge und die Arbeit mit dem Dateisystem in .NET Framework verwendete Klassen (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/classes-used-in-net-framework-file-io-and-the-file-system.md)
