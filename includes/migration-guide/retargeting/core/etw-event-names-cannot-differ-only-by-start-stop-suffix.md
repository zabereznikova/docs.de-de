---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614455"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>ETW-Ereignisnamen können sich nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden

#### <a name="details"></a>Details

In .NET Framework 4.6 und 4.6.1 löst die Runtime <xref:System.ArgumentException> aus, wenn zwei Ereignisnamen der Ereignisablaufverfolgung für Windows (ETW) sich lediglich durch das Suffix „Start“ oder „Stop“ unterscheiden (z. B. wenn ein Ereignis mit `LogUser` benannt ist und das andere mit `LogUserStart`). In diesem Fall kann die Runtime die Ereignisquelle nicht erstellen, die dann keine Protokollierung durchführen kann.

#### <a name="suggestion"></a>Vorschlag

Stellen Sie sicher, dass zwei Ereignisnamen sich nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden, um die Ausnahme zu verhindern. Diese Anforderung wird mit .NET Framework 4.6.2 entfernt. Die Runtime kann Ereignisnamen unterscheiden, die sich nur durch das Suffix „Start“ oder „Stop“ unterscheiden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6         |
| Typ    | Neuzuweisung |
