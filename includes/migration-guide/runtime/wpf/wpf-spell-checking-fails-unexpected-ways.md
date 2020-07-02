---
ms.openlocfilehash: d4f0095bc9fde98087dce528c8154d9c9ac6ddb7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621798"
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
