---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858383"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>COR_PRF_GC_ROOT_HANDLE-Elemente werden nicht vom Profiler aufgezählt

|   |   |
|---|---|
|Details|In .NET Framework 4.5.1 gibt die Profilerstellungs-API <code>RootReferences2()</code> fälschlicherweise nie <code>COR_PRF_GC_ROOT_HANDLE</code> zurück (stattdessen wird <code>COR_PRF_GC_ROOT_OTHER</code> zurückgegeben). Dieses Problem ist seit .NET Framework 4.6 behoben.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|
|`Scope`|Nebenversion|
|Version|4.5.1|
|Geben Sie Folgendes ein:|Laufzeit|
