---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497475"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a>WPF erzeugt einen „wiptis.exe“-Prozess, der die Maus sperren kann

#### <a name="details"></a>Details

Mit Version 4.5.2 wurde ein Problem eingeführt, durch das <code>wisptis.exe</code> erzeugt wird. Hierdurch kann die Mauseingabe gesperrt werden.

#### <a name="suggestion"></a>Vorschlag

Eine Problembehebung steht in einem Service Release von .NET Framework 4.5.2 (Hotfixrollup 3026376) oder durch ein Upgrade auf .NET Framework 4.6 zur Verfügung.

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
