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
ms.openlocfilehash: f0e334c75afee60591db2b4e1f45cf0ec753ee2e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141647"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="920cc-102">ICorProfilerFunctionEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="920cc-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="920cc-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="920cc-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="920cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="920cc-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="920cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="920cc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="920cc-106">[in] Die Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="920cc-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="920cc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="920cc-107">Return Value</span></span>  
 <span data-ttu-id="920cc-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="920cc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="920cc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="920cc-109">HRESULT</span></span>|<span data-ttu-id="920cc-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="920cc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="920cc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="920cc-111">S_OK</span></span>|`celt` <span data-ttu-id="920cc-112">-Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="920cc-112">elements were skipped.</span></span>|  
|<span data-ttu-id="920cc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="920cc-113">S_FALSE</span></span>|<span data-ttu-id="920cc-114">Weniger als `celt` Elemente übersprungen wurden, was bedeutet, dass keine Elemente mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="920cc-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="920cc-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="920cc-115">Remarks</span></span>  
 <span data-ttu-id="920cc-116">Die neue Position der Cursor des Enumerators ist (aktuelle Position) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="920cc-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="920cc-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="920cc-117">Requirements</span></span>  
 <span data-ttu-id="920cc-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="920cc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="920cc-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="920cc-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="920cc-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="920cc-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="920cc-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="920cc-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="920cc-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="920cc-122">See also</span></span>

- [<span data-ttu-id="920cc-123">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="920cc-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="920cc-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="920cc-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
