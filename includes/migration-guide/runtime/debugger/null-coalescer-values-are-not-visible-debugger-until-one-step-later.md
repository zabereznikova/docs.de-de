---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858597"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>NULL-Zusammenfügungswerte werden erst im nächsten Schritt angezeigt

|   |   |
|---|---|
|Details|Durch einen Fehler in .NET Framework 4.5 werden Werte, die über einen zusammenfügenden NULL-Vorgang festgelegt werden, nicht unmittelbar im Anschluss an die Zuweisung im Debugger angezeigt, wenn sie auf einer 64-Bit-Version des Frameworks ausgeführt werden.|
|Vorschlag|Wenn Sie im Debugger einen zusätzlichen Schritt ausführen, wird der lokale Wert bzw. der Feldwert ohne Probleme aktualisiert. Dieses Problem wurde auch in .NET Framework 4.6 behoben und sollte nach einem Upgrade auf diese Version nicht mehr auftreten.|
|`Scope`|Edge|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
