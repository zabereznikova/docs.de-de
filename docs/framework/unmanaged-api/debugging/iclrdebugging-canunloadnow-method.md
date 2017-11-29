---
title: ICLRDebugging::CanUnloadNow-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging.CanUnloadNow Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b013231666ca6dfde5ab16e58023da1ae2a72941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="04317-102">ICLRDebugging::CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="04317-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="04317-103">Bestimmt, ob eine Bibliothek, die vom bereitgestellt wurde ein [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Schnittstelle wird weiterhin verwendet oder können entladen werden.</span><span class="sxs-lookup"><span data-stu-id="04317-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04317-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04317-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04317-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="04317-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="04317-106">[in] Die Basisadresse eines Moduls im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="04317-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04317-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="04317-107">Return Value</span></span>  
 <span data-ttu-id="04317-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="04317-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="04317-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04317-109">HRESULT</span></span>|<span data-ttu-id="04317-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04317-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04317-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="04317-111">S_OK</span></span>|<span data-ttu-id="04317-112">Das Modul, das verweist `hmodule` entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="04317-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="04317-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="04317-113">S_FALSE</span></span>|<span data-ttu-id="04317-114">Das Modul, das verweist `hmodule` weiterhin zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="04317-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="04317-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="04317-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="04317-116">Das angegebene Modul ist kein CLR-Modul.</span><span class="sxs-lookup"><span data-stu-id="04317-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="04317-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="04317-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04317-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04317-118">Remarks</span></span>  
 <span data-ttu-id="04317-119">Diese Methode überprüft, ob alle Instanzen von `ICorDebug*` Schnittstellen veröffentlicht wurden und kein Thread ist derzeit in einem Aufruf der [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="04317-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04317-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04317-120">Requirements</span></span>  
 <span data-ttu-id="04317-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04317-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04317-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04317-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04317-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04317-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04317-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04317-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04317-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04317-125">See Also</span></span>  
 [<span data-ttu-id="04317-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="04317-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="04317-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="04317-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
