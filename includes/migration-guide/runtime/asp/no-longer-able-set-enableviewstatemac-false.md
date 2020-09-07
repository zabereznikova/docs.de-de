---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497534"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>EnableViewStateMac kann nicht mehr auf FALSE festgelegt werden

#### <a name="details"></a>Details

In ASP.NET sind die folgenden Angaben nicht mehr erlaubt: <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> oder <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>. Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen. Es sind nur Apps betroffen, die die EnableViewStateMac-Eigenschaft explizit auf <code>false</code> festlegen.

#### <a name="suggestion"></a>Vorschlag

Für EnableViewStateMac muss TRUE angenommen werden. Zudem müssen alle sich ergebenden MAC-Fehler aufgelöst werden (wie in [dieser Anleitung](https://support.microsoft.com/kb/2915218) erläutert, die in Abhängigkeit zu den Besonderheiten, die zu den MAC-Fehlern führen, mehrere Lösungen enthält).

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.5.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
