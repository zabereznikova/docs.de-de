---
ms.openlocfilehash: 09e3f0e168e0dcbe79d8ee7216f2671c67bfb87e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802966"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>Die WPF-Rechtschreibprüfungs-API schlägt auf unerwartete Weise fehl

|   |   |
|---|---|
|Details|Dies umfasst eine Reihe von Problemen mit der WPF-Rechtschreibprüfungs-API:<ul><li>Die WPF-Rechtschreibprüfungs-API löst manchmal <xref:System.Runtime.InteropServices.COMException?displayProperty=name> aus</li><li>Die WPF-Rechtschreibprüfungs-API schlägt mit der Ausnahme <xref:System.UnauthorizedAccessException> fehl, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden.</li><li>Die WPF-Rechtschreibprüfungs-API erkennt fälschlicherweise Rechtschreibfehler in zusammengesetzten deutschen Wörtern wie „Hausnummer“.</li></ul>|
|Vorschlag|Problem 1: wurde in .NET Framework 4.6.2 behoben. Problem 2: Die WPF-Rechtschreibprüfungs-API wird nicht mehr unterstützt, wenn Anwendungen mit der Einstellung „Als anderer Benutzer ausführen“ gestartet werden. Ab .NET Framework 4.6.2 stürzen Anwendungen, die auf diese Weise gestartet werden, nicht mehr unerwartet ab. Stattdessen wird nur die Rechtschreibprüfungs-API im Hintergrund deaktiviert. Problem 3: wurde in .NET Framework 4.6.2 behoben.|
|`Scope`|Edge|
|Version|4.6.1|
|Geben Sie Folgendes ein:|Laufzeit|
