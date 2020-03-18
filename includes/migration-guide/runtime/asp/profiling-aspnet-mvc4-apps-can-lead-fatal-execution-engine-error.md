---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803182"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>Bei der Profilerstellung für ASP.NET MVC4-Apps kann ein schwerwiegender Fehler der Ausführungs-Engine entstehen

|   |   |
|---|---|
|Details|Profiler, die NGEN- bzw. Profilassemblys verwenden, lösen möglicherweise beim Start von ASP.NET MVC4-Anwendungen mit Profilen einen „schwerwiegenden Fehler der Ausführungs-Engine“ aus|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.2 behoben. Der Profiler kann das Problem jedoch umgehen, indem er <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in der Ereignismaske angibt.|
|`Scope`|Edge|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
