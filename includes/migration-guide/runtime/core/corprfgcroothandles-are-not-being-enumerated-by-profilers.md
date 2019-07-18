---
ms.openlocfilehash: 8dc98b2d9c2c0b5f145ebce48cf8f5e054975c6e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858383"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a>COR_PRF_GC_ROOT_HANDLE-Elemente werden nicht vom Profiler aufgezählt

|   |   |
|---|---|
|Details|In .NET Framework 4.5.1 gibt die Profilerstellungs-API <code>RootReferences2()</code> fälschlicherweise nie <code>COR_PRF_GC_ROOT_HANDLE</code> zurück (stattdessen wird <code>COR_PRF_GC_ROOT_OTHER</code> zurückgegeben). Dieses Problem ist seit .NET Framework 4.6 behoben.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Laufzeit|

