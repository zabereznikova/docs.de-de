---
title: ICorDebug::SetManagedHandler-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 97a4a464d3dfb7b333f44ac4206bd880fd171e16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723414"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="0dc73-102">ICorDebug::SetManagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="0dc73-102">ICorDebug::SetManagedHandler Method</span></span>

<span data-ttu-id="0dc73-103">Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="0dc73-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0dc73-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dc73-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0dc73-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="0dc73-106">in Ein Zeiger auf ein [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Objekt, das das Ereignishandlerobjekt ist.</span><span class="sxs-lookup"><span data-stu-id="0dc73-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dc73-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0dc73-107">Remarks</span></span>  

 <span data-ttu-id="0dc73-108">`SetManagedHandler` muss zur Erstellungszeit aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0dc73-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="0dc73-109">Wenn die- `ICorDebugManagedCallback` Implementierung keine ausreichenden Schnittstellen zur Behandlung von debuggingereignissen für die zu debuggende Anwendung enthält, wird `SetManagedHandler` ein HRESULT E_NOINTERFACE zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0dc73-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dc73-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0dc73-110">Requirements</span></span>  

 <span data-ttu-id="0dc73-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dc73-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dc73-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dc73-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dc73-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dc73-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dc73-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dc73-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc73-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dc73-115">See also</span></span>

- [<span data-ttu-id="0dc73-116">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0dc73-116">ICorDebug Interface</span></span>](icordebug-interface.md)
