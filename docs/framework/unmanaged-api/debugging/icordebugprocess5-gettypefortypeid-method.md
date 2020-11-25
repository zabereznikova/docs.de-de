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
ms.openlocfilehash: 0ed83005bd4ab23124a458a024985d011dfce8c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717600"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="2485c-102">ICorDebugProcess5::GetTypeForTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="2485c-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>

<span data-ttu-id="2485c-103">Konvertiert einen Typbezeichner in einen ICorDebugType-Wert.</span><span class="sxs-lookup"><span data-stu-id="2485c-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2485c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2485c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2485c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2485c-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="2485c-106">in Der Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="2485c-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="2485c-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugType-Objekts.</span><span class="sxs-lookup"><span data-stu-id="2485c-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2485c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2485c-108">Remarks</span></span>  

 <span data-ttu-id="2485c-109">In einigen Fällen können Methoden, die einen Typbezeichner zurückgeben, einen NULL-Wert zurückgeben `COR_TYPEID` .</span><span class="sxs-lookup"><span data-stu-id="2485c-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="2485c-110">Wenn dieser Wert als-Argument übermittelt wird `id` , `GetTypeForTypeID` schlägt die Methode fehl und gibt zurück `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="2485c-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2485c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2485c-111">Requirements</span></span>  

 <span data-ttu-id="2485c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2485c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2485c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2485c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2485c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2485c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2485c-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2485c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2485c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2485c-116">See also</span></span>

- [<span data-ttu-id="2485c-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2485c-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="2485c-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2485c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
