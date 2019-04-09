---
title: ICorProfilerThreadEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cce96e8c6d046beba9e45c7121bf68444fd51c95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173341"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="00148-102">ICorProfilerThreadEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="00148-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="00148-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="00148-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00148-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00148-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00148-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00148-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="00148-106">[in] Die Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="00148-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00148-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="00148-107">Return Value</span></span>  
 <span data-ttu-id="00148-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="00148-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="00148-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00148-109">HRESULT</span></span>|<span data-ttu-id="00148-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00148-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00148-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="00148-111">S_OK</span></span>|`celt` <span data-ttu-id="00148-112">-Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="00148-112">elements were skipped.</span></span>|  
|<span data-ttu-id="00148-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="00148-113">S_FALSE</span></span>|<span data-ttu-id="00148-114">Weniger als `celt` Elemente übersprungen wurden, was bedeutet, dass keine Elemente mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="00148-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00148-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00148-115">Remarks</span></span>  
 <span data-ttu-id="00148-116">Die neue Position der Cursor des Enumerators ist (aktuelle Position) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="00148-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00148-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00148-117">Requirements</span></span>  
 <span data-ttu-id="00148-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00148-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00148-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00148-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00148-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00148-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="00148-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="00148-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00148-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00148-122">See also</span></span>

- [<span data-ttu-id="00148-123">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00148-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="00148-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="00148-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
