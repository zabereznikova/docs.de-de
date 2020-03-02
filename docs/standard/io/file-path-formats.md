---
title: Formate von Dateipfaden unter Windows-Systemen
ms.date: 06/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, long paths
- long paths
- path formats, Windows
ms.openlocfilehash: b3510be5d417b555d2db163636eac5ce0c0779e4
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628045"
---
# <a name="file-path-formats-on-windows-systems"></a>Formate von Dateipfaden unter Windows-Systemen

Die Member vieler Typen im <xref:System.IO>-Namespace enthalten einen `path`-Parameter, mit dem Sie einen absoluten oder relativen Pfad zu einer Dateisystemressource festlegen können. Dieser Pfad wird dann an [Windows-Dateisystem-APIs](/windows/desktop/fileio/file-systems) übergeben. In diesem Artikel werden die Formate für Dateipfade erläutert, die Sie unter Windows-Systemen verwenden können.

## <a name="traditional-dos-paths"></a>Herkömmliche DOS-Pfade

Ein standardmäßiger DOS-Pfad kann aus drei Komponenten bestehen:

- Ein Volume oder Laufwerkbuchstabe gefolgt von dem entsprechenden Trennzeichen (`:`).
- Ein Verzeichnisname. Das [Verzeichnistrennzeichen](<xref:System.IO.Path.DirectorySeparatorChar>) trennt Unterverzeichnisse innerhalb der geschachtelten Verzeichnishierarchie.
- Ein optionaler Dateiname. Das [Verzeichnistrennzeichen](<xref:System.IO.Path.DirectorySeparatorChar>) trennt den Dateipfad und den Dateinamen.

Wenn alle drei Komponenten vorhanden sind, ist der Pfad absolut. Wenn kein Volume oder Laufwerkbuchstabe angegeben ist und der Name des Verzeichnisses mit dem [Verzeichnistrennzeichen](<xref:System.IO.Path.DirectorySeparatorChar>) beginnt, ist der Pfad relativ zum Stamm des aktuellen Laufwerks. Andernfalls ist der Pfad relativ zum aktuellen Verzeichnis. In der folgenden Tabelle werden mögliche Verzeichnis- und Dateipfade veranschaulicht.

|Pfad  |Beschreibung  |
| -- | -- |
| `C:\Documents\Newsletters\Summer2018.pdf` | Ein absoluter Dateipfad aus dem Stamm vom Laufwerk „C:“ |
| `\Program Files\Custom Utilities\StringFinder.exe` | Ein absoluter Pfad aus dem Stamm des aktuellen Laufwerks |
| `2018\January.xlsx` | Ein relativer Pfad zu einer Datei in einem Unterverzeichnis des aktuellen Verzeichnisses |
| `..\Publications\TravelBrochure.pdf` | Ein relativer Pfad zu einer Datei in einem Verzeichnis, das ein Peer des aktuellen Verzeichnisses ist |
| `C:\Projects\apilibrary\apilibrary.sln` | Ein absoluter Pfad zu einer Datei aus dem Stamm vom Laufwerk „C:“ |
| `C:Projects\apilibrary\apilibrary.sln` | Ein relativer Pfad aus dem aktuellen Verzeichnis des Laufwerks „C:“ |

> [!IMPORTANT]
> Beachten Sie den Unterschied zwischen den letzten beiden Pfaden. Beide geben den optionalen Volumebezeichner (in beiden Fällen „C:“) an, jedoch beginnt der erste im Gegensatz zum zweiten mit dem Stamm des angegebenen Volume. Daher ist der erste ein absoluter Pfad aus dem Stammverzeichnis vom Laufwerk „C:“, während der zweite ein relativer Pfad aus dem aktuellen Verzeichnis vom Laufwerk „C:“ ist. Verwenden Sie das zweite Format, wenn das erste als Ursache für Fehler mit Windows-Dateipfaden bekannt ist.

Sie können ermitteln, ob ein Dateipfad absolut ist (d.h. der Pfad ist unabhängig vom aktuellen Verzeichnis und ändert sich nicht, wenn das aktuelle Verzeichnis geändert wird), indem Sie die Methode <xref:System.IO.Path.IsPathFullyQualified%2A?displayProperty=nameWthType> aufrufen. Beachten Sie, dass ein solcher Pfad relative Verzeichnissegmente (`.` und `..`) enthalten und weiterhin absolut sein kann, wenn der aufgelöste Pfad immer zum gleichen Speicherort führt.

Im folgenden Beispiel wird der Unterschied zwischen absoluten und relativen Pfaden veranschaulicht. Es wird davon ausgegangen, dass das Verzeichnis „D:\FY2018\“ vorhanden ist, und dass Sie kein aktuelles Verzeichnis für „D:\“ über die Eingabeaufforderung festgelegt haben, bevor Sie das Beispiel ausführen.

[!code-csharp[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/cs/paths.cs)]
[!code-vb[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/vb/paths.vb)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="unc-paths"></a>UNC-Pfade

UNC-Pfade (Universal Naming Convention), die für den Zugriff auf Netzwerkressourcen verwendet werden, weisen das folgende Format auf:

- Ein Server- oder Hostname, dem \\\\ vorangestellt ist. Der Servername kann ein NetBIOS-Computername oder eine IP-/FQDN-Adresse sein (IPv4 und v6 werden unterstützt).
- Ein Freigabename, der durch \\ vom Hostnamen getrennt wird. Gemeinsam bilden der Server- und Freigabename das Volume.
- Ein Verzeichnisname. Das [Verzeichnistrennzeichen](<xref:System.IO.Path.DirectorySeparatorChar>) trennt Unterverzeichnisse innerhalb der geschachtelten Verzeichnishierarchie.
- Ein optionaler Dateiname. Das [Verzeichnistrennzeichen](<xref:System.IO.Path.DirectorySeparatorChar>) trennt den Dateipfad und den Dateinamen.

Im Folgenden werden einige Beispiele für UNC-Pfade aufgeführt:

|Pfad  |Beschreibung  |
| -- | -- |
| `\\system07\C$\` | Das Stammverzeichnis des Laufwerks „C:“ auf `system07`. |
| `\\Server2\Share\Test\Foo.txt` | Die Datei „Foo.txt“ im Testverzeichnis des Volume „\\\\Server2\\Share“.|

UNC-Pfade müssen immer absolut sein. Sie können relative Verzeichnissegmente (`.` und `..`) enthalten, jedoch müssen diese Teil eines absoluten Pfads sein. Sie können relative Pfade nur verwenden, indem Sie einem Laufwerkbuchstaben einen UNC-Pfad zuordnen.

## <a name="dos-device-paths"></a>DOS-Gerätepfade

Das Windows-Betriebssystem verfügt über ein einheitliches Objektmodell, das auf alle Ressourcen, einschließlich Dateien, verweist. Sie können über das Konsolenfenster auf diese Objektpfade zugreifen. Diese werden über einen speziellen Ordner aus symbolischen Verknüpfungen, denen ältere DOS- und UNC-Pfade zugeordnet sind, für die Win32-Schicht zur Verfügung gestellt. Der Zugriff auf diesen speziellen Ordner erfolgt über die DOS-Gerätepfadsyntax, die einer der Folgenden entspricht:

`\\.\C:\Test\Foo.txt`
`\\?\C:\Test\Foo.txt`

Zusätzlich zum Identifizieren eines Laufwerks anhand des Laufwerkbuchstabens können Sie ein Volume mithilfe des Volume-GUID identifizieren. Dieser weist folgendes Format auf:

`\\.\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`
`\\?\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`

> [!NOTE]
> Die DOS-Gerätepfadsyntax wird beginnend mit .NET Core 1.1 und .NET Framework 4.6.2 von .NET-Implementierungen unterstützt, die unter Windows ausgeführt werden.

Der DOS-Gerätepfad besteht aus den folgenden Komponenten:

- Der Gerätepfadbezeichner (`\\.\` oder `\\?\`), der den Pfad als DOS-Gerätepfad identifiziert.

   > [!NOTE]
   > `\\?\` wird in allen Versionen von .NET Core und ab Version 4.6.2 von .NET Framework unterstützt.

- Ein symbolischer Link zum „echten“ Geräteobjekt (im Fall eines Laufwerknamens „C:“, im Fall eines Volume-GUID „Volume{b75e2c83-0000-0000-0000-602f00000000}“).

   Das erste Segment des DOS-Gerätepfads, nachdem der Gerätepfadbezeichner das Volume oder Laufwerk identifiziert. (Zum Beispiel `\\?\C:\` und `\\.\BootPartition\`.)

   Es gibt eine spezifische Verknüpfung für UNC-Pfade mit dem unverwechselbaren Namen `UNC`. Zum Beispiel:

  `\\.\UNC\Server\Share\Test\Foo.txt`
  `\\?\UNC\Server\Share\Test\Foo.txt`

    Bei Geräte-UNCs bildet der Abschnitt „server/share“ das Volume. Zum Beispiel entspricht der Abschnitt „server/share“ bei `\\?\server1\e:\utilities\\filecomparer\` „server1\utilities“. Dies ist beim Aufrufen einer Methode mit relativen Verzeichnissegmenten wie <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> wichtig. Es ist nicht möglich, weiter als zum Volume zu navigieren.

DOS-Gerätepfade sind definitionsgemäß absolut. Die relativen Verzeichnissegmente (`.` und `..`) sind nicht zulässig. Aktuelle Verzeichnisse haben bei Verwendung von UNC-Pfaden keine Relevanz.

## <a name="example-ways-to-refer-to-the-same-file"></a>Beispiel: Möglichkeiten zum Verweisen auf dieselbe Datei

Im folgenden Beispiel werden einige Möglichkeiten zum Verweisen auf eine Datei veranschaulicht, wenn Sie die APIs des <xref:System.IO>-Namespace verwenden. Im Beispiel wird ein <xref:System.IO.FileInfo>-Objekt instanziiert und dessen <xref:System.IO.FileInfo.Name>- und <xref:System.IO.FileInfo.Length>-Eigenschaften verwendet, um den Dateinamen und die Dateigröße anzuzeigen.

[!code-csharp[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/cs/file-refs.cs)]
[!code-vb[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/vb/file-refs.vb)]

## <a name="path-normalization"></a>Pfadnormalisierung

Die meisten Pfade, die an Windows-APIs übergeben werden, werden normalisiert. Während der Normalisierung führt Windows die folgenden Schritte durch:

- Der Pfad wird identifiziert.
- Das aktuelle Verzeichnis wird auf relative Pfade angewandt.
- Komponenten und Verzeichnistrennzeichen werden kanonisiert.
- Relative Verzeichniskomponenten werden ausgewertet (`.` für das aktuelle Verzeichnis und `..` für das übergeordnete Verzeichnis).
- Bestimmte Zeichen werden gekürzt.

Diese Normalisierung erfolgt implizit, Sie können sie jedoch explizit ausführen, indem Sie die Methode <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType> aufrufen, die einen Aufruf der [GetFullPathName()-Funktion](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) umschließt. Sie können die Windows-Funktion [GetFullPathName()](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) auch aufrufen, indem Sie „P/Invoke“ verwenden

### <a name="identifying-the-path"></a>Identifizieren des Pfads

Der erste Schritt der Pfadnormalisierung ist das Identifizieren des Pfadtyps. Pfade gehören zu einer von wenigen Kategorien:

- Gerätepfade, d.h. sie beginnen mit zwei Trennzeichen und einem Fragezeichen oder einem Punkt (`\\?` oder `\\.`).
- UNC-Pfade, d.h. sie beginnen mit zwei Trennzeichen ohne einem Fragezeichen oder Punkt.
- Absolute DOS-Pfade, d.h. sie beginnen mit einem Laufwerkbuchstaben, einem Volumetrennzeichen und einem Komponententrennzeichen (`C:\`).
- Sie legen ein Legacygerät fest (`CON`, `LPT1`).
- Sie sind relativ zum Stamm des aktuellen Laufwerks, d.h. sie beginnen mit einem einzelnen Komponententrennzeichen (`\`).
- Sie sind relativ zum aktuellen Verzeichnis eines angegebenen Laufwerks, d.h. sie beginnen mit einem Laufwerkbuchstaben, einem Volumetrennzeichen und keinem Komponententrennzeichen (`C:`).
- Sie sind relativ zum aktuellen Verzeichnis, d.h. sie beginnen mit etwas anderem (`temp\testfile.txt`).

Der Typ des Pfad bestimmt, ob ein aktuelles Verzeichnis in irgendeiner Weise angewendet wird. Er bestimmt auch den „Stamm“ des Pfads.

### <a name="handling-legacy-devices"></a>Handhaben von Legacygeräten

Wenn der Pfad ein DOS-Legacygerät wie `CON`, `COM1` oder `LPT1` ist, wird er durch Voranstellen von `\\.\` in einen Gerätepfad konvertiert und zurückgegeben.

Ein Pfad, der mit einem Legacygerätenamen beginnt, wird von der Methode <xref:System.IO.Path.GetFullPath(System.String)?displayProperty=nameWithType> immer als Legacygerät interpretiert. Beispielsweise ist der DOS-Gerätepfad für `CON.TXT``\\.\CON`, und der DOS-Gerätepfad für `COM1.TXT\file1.txt` ist `\\.\COM1`.

### <a name="applying-the-current-directory"></a>Anwenden des aktuellen Verzeichnisses

Wenn ein Pfad nicht absolut ist, wendet Windows das aktuelle Verzeichnis an. Das aktuelle Verzeichnis wird nicht auf UNC- und Gerätepfade angewendet. Auch nicht auf ein volles Laufwerk mit dem Trennzeichen C:\\.

Wenn der Pfad mit einem einzelnen Komponententrennzeichen beginnt, wird das Laufwerk des aktuellen Verzeichnisses angewendet. Wenn der Gerätepfad beispielsweise `\utilities` entspricht und das aktuelle Verzeichnis `C:\temp\` ist, erzeugt die Normalisierung `C:\utilities`.

Wenn der Pfad mit einem Laufwerkbuchstaben, einem Volumetrennzeichen und keinem Komponententrennzeichen beginnt, wird das letzte über die Befehlsshell festgelegte aktuelle Verzeichnis für das angegebene Laufwerk angewendet. Wenn das letzte aktuelle Verzeichnis nicht festgelegt wurde, wird nur das Laufwerk angewendet. Wenn der Dateipfad beispielsweise `D:sources` entspricht, das aktuelle Verzeichnis `C:\Documents\` ist, und das letzte aktuelle Verzeichnis auf Laufwerk „D:“ `D:\sources\` war, ist das Ergebnis `D:\sources\sources`. Diese „zum Laufwerk relativen“ Pfade sind eine häufige Ursache für Logikfehler beim Programm und Skript. Die Annahme, dass ein Pfad, der mit einem Buchstaben und einem Doppelpunkt beginnt, nicht relativ ist, ist offensichtlich falsch.

Wenn der Pfad mit etwas anderem als einem Trennzeichen beginnt, werden das aktuelle Laufwerk und das aktuelle Verzeichnis angewendet. Wenn der Pfad beispielsweise `filecompare` entspricht, und das aktuelle Verzeichnis `C:\utilities\` ist, ist das Ergebnis `C:\utilities\filecompare\`.

> [!IMPORTANT]
> Relative Pfade sind in Multithreadanwendungen gefährlich (d.h. in den meisten Anwendungen), da das aktuelle Verzeichnis eine prozessspezifische Einstellung ist. Jeder Thread kann das aktuelle Verzeichnis jederzeit ändern. Beginnend mit .NET Core 2.1 können Sie die Methode <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> aufrufen, um einen absoluten Pfad von einem relativen Pfad und dem Basispfad (dem aktuellen Verzeichnis) abzurufen, gegen die Sie auflösen möchten.

### <a name="canonicalizing-separators"></a>Kanonisierende Trennzeichen

Alle führenden Schrägstriche (`/`) werden in das standardmäßige Trennzeichen von Windows konvertiert, den umgekehrten Schrägstrich (`\`). Wenn sie vorhanden sind, wird eine Reihe von Schrägstrichen, die auf die ersten zwei Schrägstriche folgt, auf einen einzelnen Schrägstrich reduziert.

### <a name="evaluating-relative-components"></a>Auswerten relativer Komponenten

Während der Pfad verarbeitet wird, werden alle Komponenten oder Segmente ausgewertet, die aus einem oder zwei Punkten (`.` oder `..`) bestehen:

- Bei einzelnen Punkten wird das aktuelle Segment entfernt, da es auf das aktuelle Verzeichnis verweist.

- Bei zwei Punkten werden das aktuelle Segment und das übergeordnete Segment entfernt, da die zwei Punkte auf das übergeordnetes Verzeichnis verweisen.

   Übergeordnete Verzeichnisse werden nur entfernt, wenn sie sich nicht nach dem Stamm des Pfads befinden. Der Stamm des Pfads ist abhängig von der Art des Pfads. Für DOS-Pfade ist es das Laufwerk (`C:\`), für UNC-Pfade ist es „server/share“ (`\\Server\Share`) und für Gerätepfade ist es das Gerätepfadpräfix (`\\?\` oder `\\.\`).

### <a name="trimming-characters"></a>Entfernen von Zeichen

Zusätzlich zu den Ausführungen von Trennzeichen und Segmenten, die weiter oben entfernt wurden, werden einige zusätzliche Zeichen während der Normalisierung entfernt:

- Wenn ein Segment mit einem einzelnen Punkt endet, wird der Punkt entfernt. (Im vorherigen Schritt wurde ein Segment aus einem oder zwei Punkten normalisiert. Ein Segment aus mindestens drei Punkten wird nicht normalisiert. Tatsächlich ist das ein gültiger Datei- oder Verzeichnisname.)

- Wenn der Pfad nicht mit einem Trennzeichen endet, werden alle nachfolgenden Punkte und Leerzeichen (U+0020) entfernt. Wenn das letzte Segment nur aus einem oder zwei Punkten besteht, unterliegt es den oben genannten Regeln für relative Komponenten.

   Diese Regel bedeutet, dass Sie einen Verzeichnisnamen mit einem nachfolgendem Leerzeichen erstellen können, indem Sie nach dem Leerzeichen ein Trennzeichen hinzufügen.

   > [!IMPORTANT]
   > Sie sollten **nie** Verzeichnisse oder Dateinamen mit nachstehenden Leerzeichen erstellen. Nachstehende Leerzeichen machen es schwer, wenn nicht sogar unmöglich, auf ein Verzeichnis zuzugreifen. Außerdem treten häufig Fehler auf, wenn Anwendungen versuchen, Verzeichnisse oder Dateien zu verarbeiten, deren Namen nachstehende Leerzeichen enthalten.

## <a name="skipping-normalization"></a>Überspringen der Normalisierung

Normalerweise werden alle Pfade, die an die Windows-API übergeben werden, effektiv an die [GetFullPathName-Funktion](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) übergeben und normalisiert. Es gibt eine wichtige Ausnahme: ein Gerätepfad, der mit einem Fragezeichen statt einem Punkt beginnt. Sofern der Pfad nicht mit `\\?\` beginnt (beachten Sie die Verwendung des kanonischen umgekehrten Schrägstrichs), ist er normalisiert.

Warum kann es sinnvoll sein, die Normalisierung zu überspringen? Es gibt drei wichtige Gründe:

1. Um Zugriff auf Pfade zu erhalten, die zwar zulässig sind, aber normalerweise nicht verfügbar. Beispielsweise ist es auf keine andere Weise möglich, Zugriff auf eine Datei oder ein Verzeichnis namens `hidden.` zu erhalten.

1. Zur Verbesserung der Leistung, wenn Sie die Normalisierung bereits durchgeführt haben.

1. Zum Überspringen der `MAX_PATH`-Überprüfung der Pfadlänge, um Pfade zu ermöglichen, die länger als 259 Zeichen sind (nur in .NET Framework). Abgesehen von einigen Ausnahmen ist dies mit den meisten APIs möglich.

> [!NOTE]
> .NET Core verarbeitet lange Pfade implizit und führt keine `MAX_PATH`-Überprüfung durch. Die `MAX_PATH`-Überprüfung gilt nur für .NET Framework.

Das Überspringen der Normalisierung und MAX_PATH-Überprüfungen ist der einzige Unterschied zwischen den zwei Gerätepfadsyntaxen. Andernfalls sind sie identisch. Beachten Sie, dass Sie durch Überspringen der Normalisierung Pfade erstellen können, die für „normale“ Anwendungen schwer zu verarbeiten sind.

Pfade, die mit `\\?\` beginnen, werden weiterhin normalisiert, wenn Sie sie explizit an die [GetFullPathName-Funktion](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) übergeben.

Sie können Pfade mit mehr Zeichen als `MAX_PATH` übergeben, um [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) ohne `\\?\` abzurufen. Beliebige Pfadlängen werden bis zur maximalen Länge von Zeichenfolgen unterstützt, die Windows verarbeiten kann.

## <a name="case-and-the-windows-file-system"></a>Groß-/Kleinbuchstaben im Windows-Dateisystem

Dass Pfad- und Verzeichnisnamen die Groß-/Kleinschreibung ignorieren, ist eine Besonderheit vom Windows-Dateisystem, was viele Benutzer und Entwickler verwirrt, die Windows nicht verwenden. Das bedeutet, dass Verzeichnis- und Dateinamen die Schreibweise der Zeichenfolgen darstellen, mit der sie erstellt wurden. Zum Beispiel erstellt der Methodenaufruf

```csharp
Directory.Create("TeStDiReCtOrY");
```

```vb
Directory.Create("TeStDiReCtOrY")
```

ein Verzeichnis namens TeStDiReCtOrY. Wenn Sie ein Verzeichnis oder eine Datei umbenennen, um die Groß-/Kleinschreibung zu ändern, wird die entsprechende Zeichenfolge angezeigt, die Sie beim Umbenennen eingegeben haben. Der folgende Code benennt beispielweise eine Datei namens „test.txt“ in „Test.txt“ um:

[!code-csharp[case-and-renaming](~/samples/snippets/standard/io/file-names/cs/rename.cs)]
[!code-vb[case-and-renaming](~/samples/snippets/standard/io/file-names/vb/rename.vb)]

Allerdings berücksichtigen Vergleiche von Verzeichnis- und Dateinamen die Groß-/Kleinschreibung nicht. Wenn Sie nach einer Datei namens „test.txt“ suchen, ignorieren .NET-Dateisystem-APIs die Groß-/Kleinschreibung für Vergleiche. „Test.txt“, „TEST.TXT“, „test.TXT“ und beliebige andere Kombinationen aus Groß- und Kleinbuchstaben entsprechen „test.txt“.
