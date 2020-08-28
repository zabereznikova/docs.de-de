---
ms.openlocfilehash: faf9459ab9002e6149560e2a3452265fa246bf6b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720192"
---
### <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a>Ordnungsgemäße Analyse von URI-Pfaden mit Nicht-ASCII-Zeichen unter UNIX

Es wurde ein Fehler in der <xref:System.Uri?displayProperty=fullName>-Klasse behoben, sodass absolute URI-Pfade, die Nicht-ASCII-Zeichen enthalten, jetzt auf UNIX-Plattformen korrekt analysiert werden.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen werden absolute URI-Pfade, die Nicht-ASCII-Zeichen enthalten, auf UNIX-Plattformen falsch analysiert, und Segmente des Pfads werden dupliziert. (Absolute Pfade beginnen mit „/“.) Das Analyseproblem wurde für .NET 5.0 behoben. Wenn Sie von einer früheren Version von .NET zu .NET 5.0 oder höher wechseln, erhalten Sie unterschiedliche Werte, die von <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType> oder anderen <xref:System.Uri>-Membern erzeugt werden.

Beachten Sie bei der Ausführung unter UNIX die Ausgabe des folgenden Codes.

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

Ausgabe bei der vorherigen .NET-Version:

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

Ausgabe bei .NET 5.0 oder einer höheren Version:

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie Code verwenden, der die duplizierten Pfadsegmente erwartet und berücksichtigt, können Sie diesen Code entfernen.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
