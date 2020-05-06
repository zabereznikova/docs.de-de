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
ms.openlocfilehash: 16d15101534b88d7da4093dab73b48b5c09a192c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860400"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="7e410-102">ICLRDebugging::CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="7e410-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="7e410-103">Bestimmt, ob eine Bibliothek, die von einer [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle bereitgestellt wurde, noch verwendet wird oder entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7e410-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e410-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e410-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e410-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e410-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="7e410-106">in Die Basisadresse eines Moduls im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="7e410-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e410-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7e410-107">Return Value</span></span>  
 <span data-ttu-id="7e410-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7e410-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7e410-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e410-109">HRESULT</span></span>|<span data-ttu-id="7e410-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7e410-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e410-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e410-111">S_OK</span></span>|<span data-ttu-id="7e410-112">Das Modul, auf das von `hmodule` verwiesen wird, kann entladen werden.</span><span class="sxs-lookup"><span data-stu-id="7e410-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="7e410-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7e410-113">S_FALSE</span></span>|<span data-ttu-id="7e410-114">Das Modul, auf das von `hmodule` verwiesen wird, wird weiterhin verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e410-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="7e410-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="7e410-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="7e410-116">Das gekennzeichnete Modul ist kein CLR-Modul.</span><span class="sxs-lookup"><span data-stu-id="7e410-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7e410-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7e410-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e410-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e410-118">Remarks</span></span>  
 <span data-ttu-id="7e410-119">Diese Methode überprüft, ob alle Instanzen von `ICorDebug*` Schnittstellen freigegeben wurden und derzeit kein Thread in einem Aufrufen der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode ist.</span><span class="sxs-lookup"><span data-stu-id="7e410-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e410-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e410-120">Requirements</span></span>  
 <span data-ttu-id="7e410-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e410-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e410-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e410-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e410-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e410-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e410-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e410-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e410-125">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7e410-125">See also</span></span>

- [<span data-ttu-id="7e410-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7e410-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7e410-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7e410-127">Debugging</span></span>](index.md)
