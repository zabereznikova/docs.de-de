---
ms.openlocfilehash: 8049bf01bc10c5913fa11b25e49afd1b1317eecc
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802966"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>Die WPF-Rechtschreibprüfungs-API schlägt auf unerwartete Weise fehl

|   |   |
|---|---|
|Details|Dies umfasst eine Reihe von Problemen mit der WPF-Rechtschreibprüfungs-API:<ul><li>Die WPF-Rechtschreibprüfungs-API löst manchmal <xref:System.Runtime.InteropServices.COMException?displayProperty=name> aus</li><li>Die WPF-Rechtschreibprüfungs-API schlägt mit der Ausnahme <xref:System.UnauthorizedAccessException> fehl, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden.</li><li>Die WPF-Rechtschreibprüfungs-API erkennt fälschlicherweise Rechtschreibfehler in zusammengesetzten deutschen Wörtern wie „Hausnummer“.</li></ul>|
|Vorschlag|Problem 1: wurde in .NET Framework 4.6.2 behoben. Problem 2: Die WPF-Rechtschreibprüfungs-API wird nicht mehr unterstützt, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden. Ab .NET Framework 4.6.2 stürzen Anwendungen, die auf diese Weise gestartet werden, nicht mehr unerwartet ab. Stattdessen wird nur die Rechtschreibprüfungs-API im Hintergrund deaktiviert. Problem 3: wurde in .NET Framework 4.6.2 behoben.|
|Bereich|Microsoft Edge|
|Version|4.6.1|
|Typ|Laufzeit|

