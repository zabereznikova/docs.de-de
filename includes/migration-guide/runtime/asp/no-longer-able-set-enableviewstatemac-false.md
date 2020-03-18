---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803194"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>EnableViewStateMac kann nicht mehr auf FALSE festgelegt werden

|   |   |
|---|---|
|Details|In ASP.NET sind die folgenden Angaben nicht mehr erlaubt: <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> oder <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>. Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen. Es sind nur Apps betroffen, die die EnableViewStateMac-Eigenschaft explizit auf <code>false</code> festlegen.|
|Vorschlag|Für EnableViewStateMac muss TRUE angenommen werden. Zudem müssen alle sich ergebenden MAC-Fehler aufgelöst werden (wie in [dieser Anleitung](https://support.microsoft.com/kb/2915218) erläutert, die in Abhängigkeit zu den Besonderheiten, die zu den MAC-Fehlern führen, mehrere Lösungen enthält).|
|`Scope`|Major|
|Version|4.5.2|
|Geben Sie Folgendes ein:|Laufzeit|
