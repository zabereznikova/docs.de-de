---
title: 'ICorProfilerInfo10:: resumeruntime'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.ResumeRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 41e95a9f3ad34853f9cd71fa2cb81d3fca0fb2cd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540563"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="dfada-102">ICorProfilerInfo10:: resumeruntime-Methode</span><span class="sxs-lookup"><span data-stu-id="dfada-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="dfada-103">Setzt die Laufzeit fort, ohne eine GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dfada-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="dfada-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfada-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="dfada-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfada-105">Requirements</span></span>

<span data-ttu-id="dfada-106">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="dfada-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="dfada-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dfada-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="dfada-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfada-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="dfada-109">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfada-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dfada-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfada-110">See also</span></span>

- [<span data-ttu-id="dfada-111">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dfada-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
