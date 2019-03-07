---
title: ICorDebugValue::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a9ff2c94c98a5acc930d68e648b0ea577a82c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492308"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="b1f94-102">ICorDebugValue::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="b1f94-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="b1f94-103">Ruft die Größe des dieses "ICorDebugValue"-Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="b1f94-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1f94-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1f94-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1f94-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b1f94-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="b1f94-106">[out] Die Größe des dieses Wertobjekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b1f94-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1f94-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1f94-107">Remarks</span></span>  
 <span data-ttu-id="b1f94-108">Wenn der Typ des Werts ein Verweistyp ist, gibt diese Methode auf, die Größe des Zeigers, anstatt die Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="b1f94-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="b1f94-109">Die `ICorDebugValue::GetSize` Methodenrückgabe `COR_E_OVERFLOW` für Objekte, die größer als 4 GB auf 64-Bit-Plattformen sind.</span><span class="sxs-lookup"><span data-stu-id="b1f94-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="b1f94-110">Verwenden der [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methode stattdessen für Objekte, die größer sind als 4 GB.</span><span class="sxs-lookup"><span data-stu-id="b1f94-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1f94-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1f94-111">Requirements</span></span>  
 <span data-ttu-id="b1f94-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1f94-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1f94-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1f94-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1f94-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1f94-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1f94-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1f94-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1f94-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1f94-116">See also</span></span>

- [<span data-ttu-id="b1f94-117">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="b1f94-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
