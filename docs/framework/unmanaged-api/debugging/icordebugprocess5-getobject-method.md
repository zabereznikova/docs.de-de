---
title: ICorDebugProcess5::GetObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: e4d297023d96de83965c3d04ca9efe2613fd54d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084446"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="7a074-102">ICorDebugProcess5::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="7a074-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="7a074-103">Konvertiert eine Objekt Adresse in ein ICorDebugObjectValue-Objekt.</span><span class="sxs-lookup"><span data-stu-id="7a074-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a074-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a074-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a074-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a074-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="7a074-106">in Die Objekt Adresse.</span><span class="sxs-lookup"><span data-stu-id="7a074-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="7a074-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugObjectValue-Objekts.</span><span class="sxs-lookup"><span data-stu-id="7a074-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a074-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a074-108">Remarks</span></span>  
 <span data-ttu-id="7a074-109">Wenn `addr` nicht auf ein gültiges verwaltetes Objekt zeigt, gibt die `GetObject`-Methode `E_FAIL`zurück.</span><span class="sxs-lookup"><span data-stu-id="7a074-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a074-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a074-110">Requirements</span></span>  
 <span data-ttu-id="7a074-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a074-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a074-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a074-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a074-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a074-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a074-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a074-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a074-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a074-115">See also</span></span>

- [<span data-ttu-id="7a074-116">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a074-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="7a074-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7a074-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
