---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620213"
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
