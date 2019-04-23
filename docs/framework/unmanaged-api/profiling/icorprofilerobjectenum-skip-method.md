---
title: ICorProfilerObjectEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bcc837fede7e7db59bdf88a0b5434a7c1924335
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210944"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="a17e0-102">ICorProfilerObjectEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="a17e0-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="a17e0-103">Setzt den Cursor über dieser Enumerator aus seiner aktuellen Position an, damit an, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="a17e0-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a17e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a17e0-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a17e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a17e0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a17e0-106">[in] Die Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a17e0-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a17e0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a17e0-107">Remarks</span></span>  
 <span data-ttu-id="a17e0-108">Die neue Position der Cursor des Enumerators: (aktuelle Position) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="a17e0-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a17e0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a17e0-109">Requirements</span></span>  
 <span data-ttu-id="a17e0-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a17e0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a17e0-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a17e0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a17e0-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a17e0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a17e0-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a17e0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17e0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a17e0-114">See also</span></span>

- [<span data-ttu-id="a17e0-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a17e0-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
