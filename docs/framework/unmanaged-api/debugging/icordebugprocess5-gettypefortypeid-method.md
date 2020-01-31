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
ms.openlocfilehash: bb25c9235e4fcded5c230d2d417b9d41bbdd9b19
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792342"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="7eb18-102">ICorDebugProcess5::GetTypeForTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="7eb18-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="7eb18-103">Konvertiert einen Typbezeichner in einen ICorDebugType-Wert.</span><span class="sxs-lookup"><span data-stu-id="7eb18-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eb18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eb18-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7eb18-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="7eb18-106">in Der Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="7eb18-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="7eb18-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugType-Objekts.</span><span class="sxs-lookup"><span data-stu-id="7eb18-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eb18-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7eb18-108">Remarks</span></span>  
 <span data-ttu-id="7eb18-109">In einigen Fällen können Methoden, die einen Typbezeichner zurückgeben, einen NULL-`COR_TYPEID` Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7eb18-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="7eb18-110">Wenn dieser Wert als `id` Argument übermittelt wird, schlägt die `GetTypeForTypeID` Methode fehl und gibt `E_FAIL`zurück.</span><span class="sxs-lookup"><span data-stu-id="7eb18-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb18-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7eb18-111">Requirements</span></span>  
 <span data-ttu-id="7eb18-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb18-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eb18-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7eb18-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eb18-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eb18-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eb18-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb18-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb18-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7eb18-116">See also</span></span>

- [<span data-ttu-id="7eb18-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eb18-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="7eb18-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7eb18-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
