---
ms.openlocfilehash: 18718ebc934e0175c20411055b8c0a90ef6b175f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539472"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a>Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows

.NET 5.0 und höhere Versionen verwenden bei der Ausführung unter dem Windows 10-Update vom Mai 2019 oder später [ICU](http://site.icu-project.org/home)-Bibliotheken (International Components for Unicode, internationale Komponenten für Unicode) für die Globalisierungsfunktionalität.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor wurden in .NET-Bibliotheken [NLS](/windows/win32/intl/national-language-support)-APIs (National Language Support, Unterstützung der nationalen Sprache) für die Globalisierungsfunktionalität verwendet. Beispielsweise wurden NLS-Funktionen verwendet, um Kulturdaten wie z. B. Datums- und Uhrzeitformat-Muster abzurufen, Zeichenfolgen zu vergleichen und Groß-/Kleinschreibung von Zeichenfolgen gemäß der entsprechenden Kultur auszuführen.

Ab .NET 5.0 verwenden .NET-Bibliotheken [ICU](http://site.icu-project.org/home)-Globalisierungs-APIs, wenn eine App unter dem Windows 10-Update vom Mai 2019 oder später ausgeführt wird. Das Windows 10-Update von Mai 2019 und spätere Versionen werden mit der nativen ICU-Bibliothek ausgeliefert. Wenn die .NET-Runtime ICU nicht laden kann, verwendet sie stattdessen NLS.

Diese Änderung wurde aus zwei Gründen eingeführt:

- Apps haben auf verschiedenen Plattformen einschließlich Linux, macOS und Windows das gleiche Globalisierungsverhalten.
- Apps können das Globalisierungsverhalten steuern, indem sie benutzerdefinierte ICU-Bibliotheken verwenden.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0 Preview 4

#### <a name="recommended-action"></a>Empfohlene Aktion

Auf der Seite des Entwicklers ist keine Aktion erforderlich. Wenn Sie jedoch weiterhin NLS-Globalisierungs-APIs verwenden möchten, können Sie einen [Runtimeschalter festlegen](../../../../docs/core/run-time-config/globalization.md#nls), um zu diesem Verhalten zurückzukehren. Weitere Informationen zu den verfügbaren Schaltern finden Sie im Artikel [.NET-Globalisierung und ICU](../../../../docs/standard/globalization-localization/globalization-icu.md).

#### <a name="category"></a>Kategorie

Globalisierung

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- Die meisten Typen im <xref:System.Globalization?displayProperty=fullName>-Namespace

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
