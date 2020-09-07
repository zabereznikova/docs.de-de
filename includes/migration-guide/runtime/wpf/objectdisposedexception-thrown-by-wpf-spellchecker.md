---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496602"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme

#### <a name="details"></a>Details

WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=fullName> aus. Dies wurde in WPF für .NET Framework 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden. Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.

#### <a name="suggestion"></a>Vorschlag

Upgrade auf .NET Framework 4.7

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
