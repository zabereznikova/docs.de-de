---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497257"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>Die WPF-Rechtschreibprüfungs-API schlägt auf unerwartete Weise fehl

#### <a name="details"></a>Details

Dies umfasst eine Reihe von Problemen mit der WPF-Rechtschreibprüfungs-API:<ul><li>Die WPF-Rechtschreibprüfungs-API löst manchmal <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName> aus</li><li>Die WPF-Rechtschreibprüfungs-API schlägt mit der Ausnahme <xref:System.UnauthorizedAccessException> fehl, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden.</li><li>Die WPF-Rechtschreibprüfungs-API erkennt fälschlicherweise Rechtschreibfehler in zusammengesetzten deutschen Wörtern wie „Hausnummer“.</li></ul>

#### <a name="suggestion"></a>Vorschlag

Problem 1: wurde in .NET Framework 4.6.2 behoben. Problem 2: Die WPF-Rechtschreibprüfungs-API wird nicht mehr unterstützt, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden. Ab .NET Framework 4.6.2 stürzen Anwendungen, die auf diese Weise gestartet werden, nicht mehr unerwartet ab. Stattdessen wird nur die Rechtschreibprüfungs-API im Hintergrund deaktiviert. Problem 3: wurde in .NET Framework 4.6.2 behoben.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6.1|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
