---
title: ICorDebugProcess5::GetTypeForTypeID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13498c58c7625edfa4954b8da8837f1bd60c976d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423415"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="30043-102">ICorDebugProcess5::GetTypeForTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="30043-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="30043-103">Konvertiert einen Typbezeichner auf einen ICorDebugType-Wert.</span><span class="sxs-lookup"><span data-stu-id="30043-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30043-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30043-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30043-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30043-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="30043-106">[in] Der Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="30043-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="30043-107">[out] Ein Zeiger auf die Adresse eines ICorDebugType-Objekts.</span><span class="sxs-lookup"><span data-stu-id="30043-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30043-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30043-108">Remarks</span></span>  
 <span data-ttu-id="30043-109">In einigen Fällen gelegten Methoden, die Typ-ID zurückgeben Null `COR_TYPEID` Wert.</span><span class="sxs-lookup"><span data-stu-id="30043-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="30043-110">Wenn dieser Wert, als übergeben wird die `id` Argument, das `GetTypeForTypeID` Methode fehlschlagen und zurückgegeben `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="30043-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30043-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30043-111">Requirements</span></span>  
 <span data-ttu-id="30043-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30043-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30043-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30043-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30043-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30043-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30043-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30043-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30043-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30043-116">See Also</span></span>  
 [<span data-ttu-id="30043-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30043-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="30043-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="30043-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
