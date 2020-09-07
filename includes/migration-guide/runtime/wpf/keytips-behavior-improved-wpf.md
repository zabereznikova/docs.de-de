---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497623"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Besseres KeyTips-Verhalten in WPF

#### <a name="details"></a>Details

Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht. Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend. Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.

#### <a name="suggestion"></a>Vorschlag

Nicht zutreffend

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
