---
title: 'Breaking Change: Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, bei dem die in RFC 6265 definierten Algorithmen für die Pfadverarbeitung für die Klassen „Cookie“ und „CookieContainer“ implementiert wurden.
ms.date: 08/18/2020
ms.openlocfilehash: 4aea06f434c4bbbef7d94b4b39ff647dd954745e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759397"
---
# <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform

In [RFC 6265](https://tools.ietf.org/html/rfc6265) definierte Pfadverarbeitungsalgorithmen wurden für die Klassen <xref:System.Net.Cookie> und <xref:System.Net.CookieContainer> implementiert.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

- Die Eigenschaft <xref:System.Net.Cookie.Path> ist kein erforderliches Präfix für den Anforderungspfad mehr.
- Die Berechnung des Standardwerts von <xref:System.Net.Cookie.Path> und der Pfadabgleichalgorithmus wurden wie gemäß [Abschnitt 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) des RFC 6265 implementiert.

## <a name="recommended-action"></a>Empfohlene Maßnahme

In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen. Wenn Ihr Code jedoch von der <xref:System.Net.Cookie.Path>-Validierung abhängig wäre, müssten Sie die erforderliche Validierung in Ihren Code implementieren. Wenn Ihr Code von der Standardwertberechnung für <xref:System.Net.Cookie.Path> abhängig wäre, sollten Sie den Wert <xref:System.Net.Cookie.Path> manuell eingeben, anstatt den Standardwert zu verwenden.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

### Category

Networking

-->
