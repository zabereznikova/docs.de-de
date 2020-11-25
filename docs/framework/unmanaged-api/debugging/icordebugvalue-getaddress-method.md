---
title: ICorDebugValue::GetAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 47c0c4dfa78e85bcc83f0bb2a333955c8e8666fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728367"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="5d33b-102">ICorDebugValue::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="5d33b-102">ICorDebugValue::GetAddress Method</span></span>

<span data-ttu-id="5d33b-103">Ruft die Adresse dieses ICorDebugValue-Objekts ab, das gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="5d33b-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d33b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d33b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d33b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d33b-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="5d33b-106">vorgenommen Zeiger auf ein- `CORDB_ADDRESS` Objekt, das die Adresse dieses Wert Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="5d33b-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d33b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d33b-107">Remarks</span></span>  

 <span data-ttu-id="5d33b-108">Wenn der Wert nicht verfügbar ist, wird 0 (null) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5d33b-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="5d33b-109">Dies kann vorkommen, wenn der Wert mindestens teilweise in Registern oder in einem Garbage Collector handle () gespeichert ist `GCHandle` .</span><span class="sxs-lookup"><span data-stu-id="5d33b-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d33b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5d33b-110">Requirements</span></span>  

 <span data-ttu-id="5d33b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d33b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d33b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d33b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d33b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d33b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d33b-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d33b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d33b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d33b-115">See also</span></span>
