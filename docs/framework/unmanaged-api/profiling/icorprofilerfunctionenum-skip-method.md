---
title: ICorProfilerFunctionEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c88e52840c579173fd6202f1609dd0508d850cde
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470145"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="ec080-102">ICorProfilerFunctionEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="ec080-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="ec080-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="ec080-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec080-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec080-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec080-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec080-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ec080-106">[in] Die Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ec080-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec080-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec080-107">Return Value</span></span>  
 <span data-ttu-id="ec080-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec080-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ec080-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec080-109">HRESULT</span></span>|<span data-ttu-id="ec080-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec080-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec080-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec080-111">S_OK</span></span>|<span data-ttu-id="ec080-112">`celt` -Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="ec080-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="ec080-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ec080-113">S_FALSE</span></span>|<span data-ttu-id="ec080-114">Weniger als `celt` Elemente übersprungen wurden, was bedeutet, dass keine Elemente mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ec080-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec080-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec080-115">Remarks</span></span>  
 <span data-ttu-id="ec080-116">Die neue Position der Cursor des Enumerators ist (aktuelle Position) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="ec080-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec080-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec080-117">Requirements</span></span>  
 <span data-ttu-id="ec080-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec080-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec080-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec080-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec080-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec080-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec080-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec080-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec080-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec080-122">See also</span></span>
- [<span data-ttu-id="ec080-123">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec080-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="ec080-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ec080-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
