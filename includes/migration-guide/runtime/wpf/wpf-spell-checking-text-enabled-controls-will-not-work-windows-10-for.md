---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497766"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>Die Rechtschreibüberprüfung in textfähigen WPF-Steuerelementen funktioniert unter Windows 10 nicht für die Sprachen, die nicht in der Liste der Eingabesprachen in dem Betriebssystem aufgeführt sind

#### <a name="details"></a>Details

Bei einem Windows 10-Betriebssystem kann es sein, dass die Rechtschreibüberprüfung für textfähige WPF-Steuerelemente nicht funktioniert, da die plattformspezifischen Funktionen zur Rechtsschreibüberprüfung nur für die Sprachen verfügbar sind, die in der Liste mit den Eingabesprachen aufgeführt sind. Wenn in Windows 10 eine Sprache zu der Liste mit verfügbaren Tastaturen hinzugefügt wird, lädt Windows automatisch ein passendes Feature-On-Demand-Paket herunter, das Funktion zur Rechtschreibüberprüfung enthält, und installiert dieses. Durch das Hinzufügen der Sprache zur Eingabesprachenliste wird die Rechtschreibprüfung unterstützt.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, das die Sprache oder der Text, deren bzw. dessen Rechtschreibung überprüft werden muss, als Eingabesprache hinzugefügt werden muss, damit die Rechtschreibüberprüfung in Windows 10 funktioniert.

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
