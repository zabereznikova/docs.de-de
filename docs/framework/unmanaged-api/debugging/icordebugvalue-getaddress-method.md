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
ms.openlocfilehash: 467ba53f90081f0c3499fb22acab96b5e380a3f4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395845"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="01744-102">ICorDebugValue::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="01744-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="01744-103">Ruft die Adresse dieses ICorDebugValue-Objekts ab, das gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="01744-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01744-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01744-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01744-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01744-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="01744-106">vorgenommen Zeiger auf ein- `CORDB_ADDRESS` Objekt, das die Adresse dieses Wert Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="01744-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01744-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="01744-107">Remarks</span></span>  
 <span data-ttu-id="01744-108">Wenn der Wert nicht verfügbar ist, wird 0 (null) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="01744-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="01744-109">Dies kann vorkommen, wenn der Wert mindestens teilweise in Registern oder in einem Garbage Collector handle () gespeichert ist `GCHandle` .</span><span class="sxs-lookup"><span data-stu-id="01744-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01744-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01744-110">Requirements</span></span>  
 <span data-ttu-id="01744-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01744-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01744-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01744-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01744-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01744-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01744-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01744-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01744-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01744-115">See also</span></span>
