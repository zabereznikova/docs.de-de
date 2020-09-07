---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497351"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Deserialisierung von Objekten für mehrere Anwendungsdomänen kann einen Fehler auslösen

#### <a name="details"></a>Details

In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.

#### <a name="suggestion"></a>Vorschlag

Siehe [Entschärfung: Deserialisierung von Objekten über App-Domänen](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5.1|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
