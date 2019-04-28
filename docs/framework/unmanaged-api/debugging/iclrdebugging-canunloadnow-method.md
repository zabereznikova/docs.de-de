---
title: ICLRDebugging::CanUnloadNow-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80559ef685a2dbf48d65e0d81432a5edbd5528bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698147"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="1393e-102">ICLRDebugging::CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="1393e-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="1393e-103">Bestimmt, ob eine Bibliothek, die vom bereitgestellt wurde ein [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Schnittstelle wird immer noch verwendet oder entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1393e-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1393e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1393e-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1393e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1393e-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="1393e-106">[in] Die Basisadresse eines Moduls in den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="1393e-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1393e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1393e-107">Return Value</span></span>  
 <span data-ttu-id="1393e-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1393e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1393e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1393e-109">HRESULT</span></span>|<span data-ttu-id="1393e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1393e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1393e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1393e-111">S_OK</span></span>|<span data-ttu-id="1393e-112">Das Modul, das verweist `hmodule` entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1393e-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="1393e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1393e-113">S_FALSE</span></span>|<span data-ttu-id="1393e-114">Das Modul, das verweist `hmodule` wird immer noch verwendet.</span><span class="sxs-lookup"><span data-stu-id="1393e-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="1393e-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="1393e-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="1393e-116">Das angegebene Modul ist es sich nicht um ein CLR-Modul.</span><span class="sxs-lookup"><span data-stu-id="1393e-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="1393e-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="1393e-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1393e-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1393e-118">Remarks</span></span>  
 <span data-ttu-id="1393e-119">Diese Methode überprüft, ob alle Instanzen von `ICorDebug*` Schnittstellen veröffentlicht wurden und kein Thread befindet sich derzeit in einem Aufruf der [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="1393e-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1393e-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1393e-120">Requirements</span></span>  
 <span data-ttu-id="1393e-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1393e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1393e-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1393e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1393e-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1393e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1393e-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1393e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1393e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1393e-125">See also</span></span>

- [<span data-ttu-id="1393e-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1393e-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1393e-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1393e-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
