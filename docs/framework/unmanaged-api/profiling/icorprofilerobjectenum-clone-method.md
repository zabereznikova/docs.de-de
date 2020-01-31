---
title: ICorProfilerObjectEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: 8153dbd27e168e3a5bd8e5aeada955a0382aaf75
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868251"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="fdba5-102">ICorProfilerObjectEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="fdba5-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="fdba5-103">Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) -Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="fdba5-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdba5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdba5-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdba5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="fdba5-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="fdba5-106">vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser `ICorProfilerObjectEnum`-Schnittstelle zeigt.</span><span class="sxs-lookup"><span data-stu-id="fdba5-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="fdba5-107">Der Kopiervorgang behält seinen eigenen Enumerationszustand getrennt von diesem bei.</span><span class="sxs-lookup"><span data-stu-id="fdba5-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="fdba5-108">Die ursprüngliche Cursorposition des Kopierens ist jedoch mit der aktuellen Cursorposition dieses Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="fdba5-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdba5-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fdba5-109">Requirements</span></span>  
 <span data-ttu-id="fdba5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdba5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdba5-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fdba5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fdba5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdba5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdba5-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdba5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdba5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdba5-114">See also</span></span>

- [<span data-ttu-id="fdba5-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdba5-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
