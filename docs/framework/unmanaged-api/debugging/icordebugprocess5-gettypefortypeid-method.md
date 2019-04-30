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
ms.openlocfilehash: aeb4ad1dffe4553b243b5168037aea8b68f8244b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930207"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="0bc89-102">ICorDebugProcess5::GetTypeForTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="0bc89-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="0bc89-103">Konvertiert einen Typ-ID zu einem ICorDebugType-Wert.</span><span class="sxs-lookup"><span data-stu-id="0bc89-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bc89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bc89-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bc89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bc89-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="0bc89-106">[in] Der Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="0bc89-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="0bc89-107">[out] Ein Zeiger auf die Adresse eines ICorDebugType-Objekts.</span><span class="sxs-lookup"><span data-stu-id="0bc89-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bc89-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bc89-108">Remarks</span></span>  
 <span data-ttu-id="0bc89-109">In einigen Fällen Methoden, die Typ-ID zurückgeben können ein NULL-Wert zurückgeben `COR_TYPEID` Wert.</span><span class="sxs-lookup"><span data-stu-id="0bc89-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="0bc89-110">Wenn dieser Wert, als übergeben wird die `id` -Argument, das `GetTypeForTypeID` Methode fehlschlagen und zurückgegeben `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="0bc89-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bc89-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0bc89-111">Requirements</span></span>  
 <span data-ttu-id="0bc89-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bc89-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc89-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bc89-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bc89-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bc89-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bc89-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc89-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bc89-116">See also</span></span>

- [<span data-ttu-id="0bc89-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bc89-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="0bc89-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0bc89-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
