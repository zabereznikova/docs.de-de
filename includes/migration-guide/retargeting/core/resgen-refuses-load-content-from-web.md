---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614519"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a>Resgen lehnt das Laden von Inhalten aus dem Web ab

#### <a name="details"></a>Details

RESX-Dateien können binär formatierte Eingaben enthalten. Wenn Sie versuchen, mit Resgen eine Datei zu laden, die aus einem nicht vertrauenswürdigen Speicherort heruntergeladen wurde, schlägt das Laden der Eingabe standardmäßig fehl.

#### <a name="suggestion"></a>Vorschlag

Benutzer von Resgen, die binär formatierte Eingaben aus nicht vertrauenswürdigen Speicherorten laden müssen, können entweder die Markierung des Webs aus der Eingabedatei entfernen oder die Deaktivierungsmethode anwenden.Fügen Sie die folgende Registrierungseinstellung hinzu, um die computerweite Deaktivierungsmethode anzuwenden: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
