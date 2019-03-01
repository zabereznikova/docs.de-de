---
title: ICorDebugAppDomain2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82b58780472443874f2dae93c2d8568006db2e8a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978565"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="577fe-102">ICorDebugAppDomain2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="577fe-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="577fe-103">Stellt Methoden zum Arbeiten mit Arrays, Zeigern, Funktionszeigern und Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="577fe-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="577fe-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="577fe-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="577fe-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="577fe-105">Methods</span></span>  
  
|<span data-ttu-id="577fe-106">Methode</span><span class="sxs-lookup"><span data-stu-id="577fe-106">Method</span></span>|<span data-ttu-id="577fe-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="577fe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="577fe-108">GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="577fe-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="577fe-109">Ruft ein Array von den angegebenen Typ oder ein Zeiger oder Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="577fe-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="577fe-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="577fe-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="577fe-111">Ruft einen Zeiger auf eine Funktion, die einer bestimmten Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="577fe-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="577fe-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="577fe-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="577fe-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="577fe-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="577fe-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="577fe-114">Requirements</span></span>  
 <span data-ttu-id="577fe-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="577fe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="577fe-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="577fe-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="577fe-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="577fe-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="577fe-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="577fe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577fe-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="577fe-119">See also</span></span>
- [<span data-ttu-id="577fe-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="577fe-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
