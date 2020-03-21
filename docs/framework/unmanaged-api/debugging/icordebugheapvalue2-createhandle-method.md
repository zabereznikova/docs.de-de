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
ms.openlocfilehash: c7a1bf3cb10cbc8cdae2788b45e1badaf66a9dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178880"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="74233-102">ICorDebugHeapValue2::CreateHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="74233-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="74233-103">Erstellt ein Handle des angegebenen Typs für den Heapwert, der durch dieses ICorDebugHeapValue2-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="74233-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74233-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74233-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74233-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="74233-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="74233-106">[in] Ein Wert der CorDebugHandleType-Enumeration, der den Typ des zu erstellenden Handles angibt.</span><span class="sxs-lookup"><span data-stu-id="74233-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="74233-107">[out] Ein Zeiger auf die Adresse eines ICorDebugHandleValue-Objekts, das das neue Handle für diesen Heapwert darstellt.</span><span class="sxs-lookup"><span data-stu-id="74233-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74233-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="74233-108">Remarks</span></span>  
 <span data-ttu-id="74233-109">Das Handle wird in der Anwendungsdomäne erstellt, die dem Heapwert zugeordnet ist, und wird ungültig, wenn die Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="74233-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="74233-110">Mehrere Aufrufe dieser Funktion für denselben Heapwert erstellen mehrere Handles.</span><span class="sxs-lookup"><span data-stu-id="74233-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="74233-111">Da sich Handles auf die Leistung des Garbage Collectors auswirken, sollte sich der Debugger auf eine relativ kleine Anzahl von Handles (ca. 256) beschränken, die gleichzeitig aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="74233-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74233-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="74233-112">Requirements</span></span>  
 <span data-ttu-id="74233-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74233-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74233-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74233-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74233-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74233-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74233-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74233-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
