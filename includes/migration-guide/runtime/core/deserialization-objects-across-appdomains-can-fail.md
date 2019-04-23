---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235247"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Deserialisierung von Objekten für mehrere Anwendungsdomänen kann einen Fehler auslösen

|   |   |
|---|---|
|Details|In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.|
|Vorschlag|Siehe [Entschärfung: Deserialisierung von Objekten über App-Domänen](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)|
|Bereich|Microsoft Edge|
|Version|4.5.1|
|Typ|Laufzeit|
