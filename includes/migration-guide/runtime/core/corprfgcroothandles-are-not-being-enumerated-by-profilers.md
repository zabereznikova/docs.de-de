---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497171"
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

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
