---
title: ICorDebugManagedCallback::UnloadClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: 6efd451c6895e8fef443e2e86afa6e98279c6493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723999"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="cbc8b-102">ICorDebugManagedCallback::UnloadClass-Methode</span><span class="sxs-lookup"><span data-stu-id="cbc8b-102">ICorDebugManagedCallback::UnloadClass Method</span></span>

<span data-ttu-id="cbc8b-103">Benachrichtigt den Debugger, dass eine Klasse entladen wird.</span><span class="sxs-lookup"><span data-stu-id="cbc8b-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbc8b-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbc8b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbc8b-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="cbc8b-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die-Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="cbc8b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="cbc8b-107">in Ein Zeiger auf ein ICorDebugClass-Objekt, das die-Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="cbc8b-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbc8b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbc8b-108">Remarks</span></span>  

 <span data-ttu-id="cbc8b-109">Nach diesem-Befehl sollte nicht auf die-Klasse verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cbc8b-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbc8b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cbc8b-110">Requirements</span></span>  

 <span data-ttu-id="cbc8b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbc8b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbc8b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbc8b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbc8b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbc8b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbc8b-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbc8b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc8b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbc8b-115">See also</span></span>

- [<span data-ttu-id="cbc8b-116">LoadClass-Methode</span><span class="sxs-lookup"><span data-stu-id="cbc8b-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="cbc8b-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbc8b-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
