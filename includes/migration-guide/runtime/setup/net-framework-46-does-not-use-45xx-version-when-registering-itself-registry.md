---
ms.openlocfilehash: a9011514c7c4393ec44de2c7fae88768cdccf435
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496652"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a>.NET Framework 4.6 verwendet keine 4.5.x.x-Version bei der Registrierung

#### <a name="details"></a>Details

Der Versionsschlüssel in der Registrierung (unter <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) für .NET Framework 4.6 beginnt also mit „4.6“. Apps, die von diesen Registrierungsschlüsseln abhängig sind, damit sie wissen, welche .NET Framework-Versionen auf dem Computer installiert sind, sollten aktualisiert werden, sodass sie Version 4.6 als mögliche Version anerkennen, die mit den 4.5.x-Vorgängerversionen kompatibel ist.

#### <a name="suggestion"></a>Vorschlag

Aktualisieren Sie Apps, die über 4.5-Registrierungsschlüssel nach einer .NET Framework 4.5-Installation suchen, sodass diese auch Version 4.6 akzeptieren.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
