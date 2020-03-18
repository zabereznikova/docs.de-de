---
ms.openlocfilehash: 994876457f9745de99be30e567f400f69a0192fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "70259791"
---
### <a name="changes-in-path-normalization"></a>Änderungen an der Pfadnormalisierung

|   |   |
|---|---|
|Details|Bei Apps, die die Zielplattform .NET Framework 4.6.2 und höher verwenden, wurde im Vergleich zu früheren Versionen die Art und Weise verändert, in der die Laufzeit Pfade normalisiert. Das Normalisieren eines Pfads umfasst das Verändern der Zeichenfolge, die einen Pfad oder eine Datei identifiziert, sodass sie einem gültigen Pfad auf dem Zielbetriebssystem entspricht. Normalisierung umfasst ist in der Regel:<ul><li>Die Kanonisierung von Komponenten- und Verzeichnistrennzeichen.</li><li>Die Anwendung des aktuellen Verzeichnisses auf einen relativen Pfad.</li><li>Die Auswertung des relativen Verzeichnisses (.) oder des übergeordneten Verzeichnisses (..) in einem Pfad.</li><li>Das Verkürzen um angegebene Zeichen.</li></ul>Für Apps, die die Zielplattform .NET Framework 4.6.2 und höher verwenden, sind die folgenden Änderungen an der Pfadnormalisierung standardmäßig aktiviert:<ul><li>Die Runtime greift auf die Funktion [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) des Betriebssystems zurück, um Pfade zu normalisieren.</li><li>Die Normalisierung beinhaltet nicht mehr das Verkürzen des Endes von Verzeichnissegmenten (etwa im Fall eines Leerzeichens am Ende eines Verzeichnisnamens).</li><li>Unterstützung für Gerätepfadsyntax mit vollem Vertrauen, einschließlich `\\.\` und `\\?\` für Datei-E/A-APIs in mscorlib.dll.</li><li>Die Runtime überprüft Gerätesyntaxpfade nicht.</li><li>Die Verwendung von Gerätesyntax für den Zugriff auf alternative Datenströme wird unterstützt.</li></ul>Diese Änderungen verbessern die Leistung und ermöglichen zugleich Methoden den Zugriff auf zuvor nicht zugängliche Pfade. Apps mit der Zielplattform .NET Framework 4.6.1 und früheren Versionen, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, sind von dieser Änderung nicht betroffen.|
|Vorschlag|Apps mit der Zielplattform .NET Framework 4.6.2 oder höher können die Änderung deaktivieren und die Legacynormalisierung verwenden, indem dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei Folgendes hinzugefügt wird:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Für Apps mit der Zielplattform .NET Framework 4.6.1 oder niedriger, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, können die Änderungen an der Pfadnormalisierung aktiviert werden, indem dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
