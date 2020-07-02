---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620212"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>COR_PRF_GC_ROOT_HANDLE-Elemente werden nicht vom Profiler aufgezählt

#### <a name="details"></a>Details

In .NET Framework 4.5.1 gibt die Profilerstellungs-API <code>RootReferences2()</code> fälschlicherweise nie <code>COR_PRF_GC_ROOT_HANDLE</code> zurück (stattdessen wird <code>COR_PRF_GC_ROOT_OTHER</code> zurückgegeben). Dieses Problem ist seit .NET Framework 4.6 behoben.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5.1|
|Typ|Laufzeit|
