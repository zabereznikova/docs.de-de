---
title: ICorDebugHeapValue2::CreateHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5c5a12df5689f113857045ba4bcda696bda8f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756725"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="2b065-102">ICorDebugHeapValue2::CreateHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="2b065-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="2b065-103">Erstellt ein Handle des angegebenen Typs für den Heapwert, der von diesem ICorDebugHeapValue2-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2b065-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b065-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b065-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b065-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b065-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="2b065-106">[in] Der Wert CorDebugHandleType-Enumeration, die den Typ des zu erstellenden Handle angibt.</span><span class="sxs-lookup"><span data-stu-id="2b065-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="2b065-107">[out] Ein Zeiger auf die Adresse des ICorDebugHandleValue-Objekts, das das neue Handle für diesen Heapwert darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b065-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b065-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b065-108">Remarks</span></span>  
 <span data-ttu-id="2b065-109">Das Handle erstellt werden, in der Anwendungsdomäne, die mit dem Heapwert verknüpft ist, und es werden dadurch ungültig, wenn die Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="2b065-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="2b065-110">Mehrere Aufrufe dieser Funktion für den gleichen Heapwert erstellt mehrere Handles.</span><span class="sxs-lookup"><span data-stu-id="2b065-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="2b065-111">Da Handles auf die Leistung der Garbage Collection betreffen, sollten der Debugger selbst, um eine relativ kleine Anzahl von Handles (ca. 256) einschränken, die gleichzeitig aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="2b065-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b065-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b065-112">Requirements</span></span>  
 <span data-ttu-id="2b065-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b065-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b065-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b065-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b065-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b065-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b065-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b065-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
