---
title: ICorDebugValue::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5cf99b35d45c1dda8f187e0206e068c128f347d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="d8f5e-102">ICorDebugValue::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d8f5e-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="d8f5e-103">Ruft die Größe in Bytes des Objekts "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="d8f5e-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8f5e-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8f5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8f5e-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="d8f5e-106">[out] Die Größe in Bytes, der dieses Wertobjekt.</span><span class="sxs-lookup"><span data-stu-id="d8f5e-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8f5e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8f5e-107">Remarks</span></span>  
 <span data-ttu-id="d8f5e-108">Wenn der Typ des Werts ein Verweistyp ist, gibt diese Methode die Größe des Zeigers statt der Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="d8f5e-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="d8f5e-109">Die `ICorDebugValue::GetSize` -Methode zurückkehrt `COR_E_OVERFLOW` für Objekte, die größer als 4 GB auf 64-Bit-Plattformen sind.</span><span class="sxs-lookup"><span data-stu-id="d8f5e-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="d8f5e-110">Verwenden der [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methode stattdessen für Objekte, die sind größer als 4 GB.</span><span class="sxs-lookup"><span data-stu-id="d8f5e-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f5e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8f5e-111">Requirements</span></span>  
 <span data-ttu-id="d8f5e-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8f5e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f5e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8f5e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8f5e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8f5e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8f5e-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f5e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f5e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8f5e-116">See Also</span></span>  
    
 [<span data-ttu-id="d8f5e-117">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="d8f5e-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
