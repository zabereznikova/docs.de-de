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
ms.openlocfilehash: 41b2e009f8f017a72147232015ea2357ae922ca1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793651"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="3a2dd-102">ICLRDebugging::CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="3a2dd-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="3a2dd-103">Bestimmt, ob eine Bibliothek, die von einer [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle bereitgestellt wurde, noch verwendet wird oder entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3a2dd-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a2dd-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a2dd-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3a2dd-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="3a2dd-106">in Die Basisadresse eines Moduls im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="3a2dd-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a2dd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3a2dd-107">Return Value</span></span>  
 <span data-ttu-id="3a2dd-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a2dd-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3a2dd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a2dd-109">HRESULT</span></span>|<span data-ttu-id="3a2dd-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a2dd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a2dd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a2dd-111">S_OK</span></span>|<span data-ttu-id="3a2dd-112">Das Modul, auf das von `hmodule` verwiesen wird, kann entladen werden.</span><span class="sxs-lookup"><span data-stu-id="3a2dd-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="3a2dd-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3a2dd-113">S_FALSE</span></span>|<span data-ttu-id="3a2dd-114">Das Modul, auf das von `hmodule` verwiesen wird, wird weiterhin verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a2dd-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="3a2dd-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="3a2dd-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="3a2dd-116">Das gekennzeichnete Modul ist kein CLR-Modul.</span><span class="sxs-lookup"><span data-stu-id="3a2dd-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="3a2dd-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="3a2dd-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a2dd-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a2dd-118">Remarks</span></span>  
 <span data-ttu-id="3a2dd-119">Diese Methode überprüft, ob alle Instanzen von `ICorDebug*`-Schnittstellen freigegeben wurden und derzeit kein Thread in einem Aufrufen der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3a2dd-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a2dd-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a2dd-120">Requirements</span></span>  
 <span data-ttu-id="3a2dd-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a2dd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a2dd-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a2dd-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a2dd-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a2dd-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a2dd-124">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a2dd-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2dd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a2dd-125">See also</span></span>

- [<span data-ttu-id="3a2dd-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3a2dd-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3a2dd-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="3a2dd-127">Debugging</span></span>](index.md)
