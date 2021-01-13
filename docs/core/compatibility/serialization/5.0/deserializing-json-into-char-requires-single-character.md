---
title: 'Breaking Change: Die Deserialisierung von Char erfordert Zeichenfolgen mit einzelnem Zeichen'
description: Hier erfahren Sie mehr über die Breaking Change in .NET 5.0, bei der System.Text.Json bei der Deserialisierung in ein Char-Ziel eine Zeichenfolge mit einem einzelnen Zeichen im JSON-Format erfordert.
ms.date: 12/15/2020
ms.openlocfilehash: 39a2d25b00bf8855cfbf46a4d78b8545052703e5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633870"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a>System.Text.Json erfordert zum Deserialisieren eines Chars eine Zeichenfolge mit einem einzelnen Zeichen.

Um ein <xref:System.Char> mit <xref:System.Text.Json> erfolgreich zu deserialisieren, muss die JSON-Zeichenfolge ein einzelnes Zeichen enthalten.

## <a name="change-description"></a>Änderungsbeschreibung

In bisherigen .NET-Versionen wurde eine Zeichenfolge mit mehreren `char`-Variablen in der JSON-Datei erfolgreich in eine `char`-Eigenschaft oder ein CHAR-Feld deserialisiert. Es wird nur der erste `char` der Zeichenfolge verwendet, wie im folgenden Beispiel gezeigt:

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

In .NET 5.0 und höher bewirkt etwas anderes wie eine Zeichenfolge mit einem einzelnen `char`, dass eine <xref:System.Text.Json.JsonException>-Ausnahme ausgelöst wird, wenn es sich bei dem Deserialisierungsziel um ein `char` handelt. Die folgende Beispielzeichenfolge wird in allen .NET-Versionen erfolgreich deserialisiert:

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="reason-for-change"></a>Grund für die Änderung

Das Parsen für die Deserialisierung sollte nur erfolgreich sein, wenn die bereitgestellten Nutzdaten für den Zieltyp gültig sind. Bei einem `char`-Typ bestehen gültige Nutzdaten aus einer Zeichenfolge mit einem einzelnen `char`-Zeichen.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie JSON-Werte in ein `char`-Ziel deserialisieren, stellen Sie sicher, dass die Zeichenfolge aus einem einzelnen `char` besteht.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
