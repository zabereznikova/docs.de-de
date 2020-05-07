---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595680"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a>UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt

<xref:System.UriBuilder.Fragment?displayProperty=nameWithType> wird führenden `#`-Zeichen mehr vorangestellt, und <xref:System.UriBuilder.Query?displayProperty=nameWithType> wird führenden `?`-Zeichen nicht mehr vorangestellt, wenn ein solches Element bereits vorhanden ist.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework stellen die <xref:System.UriBuilder.Fragment?displayProperty=nameWithType>- und <xref:System.UriBuilder.Query?displayProperty=nameWithType>-Eigenschaften immer ein `#`- oder `?`-Zeichen voran, das sich nach dem gespeicherten Wert richtet. Dieses Verhalten kann zu mehreren `#`- oder `?`-Zeichen im gespeicherten Wert führen, wenn die Zeichenfolge bereits eines dieser führenden Zeichen enthält. Beispielsweise kann der Wert von <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> zu `##main` werden.

Ab .NET Core 1.0 stellen diese Eigenschaften die `#`- und `?`-Zeichen nicht mehr dem gespeicherten Wert voran, wenn diese bereits am Anfang der Zeichenfolge vorhanden sind.

#### <a name="version-introduced"></a>Eingeführt in Version

1.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Beim Festlegen der Eigenschaftswerte müssen Sie keines dieser führenden Zeichen mehr explizit entfernen. Dies ist besonders nützlich, wenn Sie Werte anfügen, da Sie die führenden `#`- oder `?`-Zeichen nicht mehr jedes Mal entfernen müssen.

Der folgende Codeausschnitt zeigt z. B. den Verhaltensunterschied zwischen .NET Framework und .NET Core.

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- In .NET Framework lautet die Ausgabe `????one=1&two=2&three=3&four=4`.
- In .NET Core lautet die Ausgabe `?one=1&two=2&three=3&four=4`.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
