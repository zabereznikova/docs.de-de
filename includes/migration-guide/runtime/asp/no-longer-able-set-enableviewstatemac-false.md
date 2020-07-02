---
ms.openlocfilehash: cecb7b2abd4f57fdaacb0ea373cc19dc3cd9b24a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620166"
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
