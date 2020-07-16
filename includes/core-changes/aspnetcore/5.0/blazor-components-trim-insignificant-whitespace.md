---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174261"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a>Blazor: Unbedeutende Leerzeichen zur Kompilierzeit aus Komponenten entfernt

Ab ASP.NET Core 5.0 Preview 7 werden vom Razor-Compiler in Blazor-Komponenten ( *.razor*-Dateien) zur Kompilierzeit unbedeutende Leerzeichen weggelassen. Weitere Informationen finden Sie unter dem Issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 7

#### <a name="old-behavior"></a>Altes Verhalten

In 3.x-Versionen von Blazor Server und Blazor WebAssembly werden Leerzeichen im Quellcode einer Komponente berücksichtigt. Textknoten, die nur Leerzeichen enthalten, werden im Dokumentobjektmodell (DOM) des Browsers auch dann gerendert, wenn dies keine visuellen Auswirkungen hat.

Sehen Sie sich den folgenden Code für eine Blazor-Komponente an:

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

Im obigen Beispiel werden zwei Leerzeichenknoten gerendert:

* Außerhalb des Codeblocks `@foreach`.
* Im Bereich des Elements `<li>`.
* Im Bereich der Ausgabe `@item.Text`.

Eine Liste mit 100 Einträgen führt zu 402 Leerzeichenknoten. Dies entspricht mehr als der Hälfte aller gerenderten Knoten, auch wenn keiner der Leerzeichenknoten eine visuelle Auswirkung auf die gerenderte Ausgabe hat.

Beim Rendern von statischem HTML-Code für Komponenten wurden Leerzeichen innerhalb eines Tags nicht beibehalten. Sehen Sie sich beispielsweise die Quelle der folgenden Komponente an:

```razor
<foo        bar="baz"     />
```

Leerzeichen werden nicht beibehalten. Die vorab gerenderte Ausgabe lautet wie folgt:

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a>Neues Verhalten

Sofern nicht die Anweisung `@preservewhitespace` mit dem Wert `true` verwendet wird, werden Leerzeichenknoten entfernt, wenn dafür Folgendes gilt:

* Stehen in einem Element am Anfang oder am Ende.
* Stehen in einem `RenderFragment`-Parameter am Anfang oder am Ende. Ein Beispiel hierfür ist untergeordneter Inhalt, der an eine andere Komponente übergeben wird.
* Stehen am Anfang oder Ende eines C#-Codeblocks, z. B. `@if` und `@foreach`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Ein Ziel für Blazor in ASP.NET Core 5.0 ist die Verbesserung der Leistung beim Rendern und Vergleichen. Für Strukturknoten mit unbedeutenden Leerzeichen wurden bei Benchmarktests bis zu 40 Prozent der Renderzeit verbraucht.

#### <a name="recommended-action"></a>Empfohlene Aktion

In den meisten Fällen ergeben sich keinerlei Auswirkungen auf das visuelle Layout der gerenderten Komponente. Das Entfernen der Leerzeichen kann sich aber auf die gerenderte Ausgabe auswirken, wenn eine CSS-Regel wie `white-space: pre` verwendet wird. Führen Sie eine der folgenden Aktionen durch, um diese Leistungsoptimierung zu deaktivieren und die Leerzeichen beizubehalten:

* Fügen Sie oben in der *.razor*-Datei die Anweisung `@preservewhitespace true` hinzu, um sie auf eine bestimmte Komponente anzuwenden.
* Fügen Sie die Anweisung `@preservewhitespace true` in einer *_Imports.razor*-Datei hinzu, um sie auf ein gesamtes Unterverzeichnis oder das gesamte Projekt anzuwenden.

In den meisten Fällen ist keine Aktion erforderlich, weil sich Anwendungen normalerweise wie gewohnt (aber schneller) verhalten. Falls das Entfernen der Leerzeichen für eine bestimmte Komponente zu Problemen führt, sollten Sie darin `@preservewhitespace true` nutzen, um diese Optimierung zu deaktivieren.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
