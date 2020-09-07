---
ms.openlocfilehash: c679cb2603d39f580203d9373d76481e904e6c1d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497896"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>Bei der Profilerstellung für ASP.NET MVC4-Apps kann ein schwerwiegender Fehler der Ausführungs-Engine entstehen

#### <a name="details"></a>Details

Profiler, die NGEN- bzw. Profilassemblys verwenden, lösen möglicherweise beim Start von ASP.NET MVC4-Anwendungen mit Profilen einen „schwerwiegenden Fehler der Ausführungs-Engine“ aus

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.5.2 behoben. Der Profiler kann das Problem jedoch umgehen, indem er <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in der Ereignismaske angibt.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
