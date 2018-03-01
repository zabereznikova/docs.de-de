---
title: ICorDebugAppDomain2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c811107fcf32696aee17810af06ac0b2ddc9102d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="659fc-102">ICorDebugAppDomain2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="659fc-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="659fc-103">Stellt Methoden zum Arbeiten mit Arrays, Zeigern, Funktionszeigern und Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="659fc-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="659fc-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="659fc-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="659fc-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="659fc-105">Methods</span></span>  
  
|<span data-ttu-id="659fc-106">Methode</span><span class="sxs-lookup"><span data-stu-id="659fc-106">Method</span></span>|<span data-ttu-id="659fc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="659fc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="659fc-108">GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="659fc-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="659fc-109">Ruft ein Array des angegebenen Typs oder ein Zeiger oder Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="659fc-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="659fc-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="659fc-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="659fc-111">Ruft einen Zeiger auf eine Funktion, die einer bestimmten Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="659fc-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="659fc-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="659fc-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="659fc-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="659fc-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="659fc-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="659fc-114">Requirements</span></span>  
 <span data-ttu-id="659fc-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="659fc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="659fc-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="659fc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="659fc-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="659fc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="659fc-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="659fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659fc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="659fc-119">See Also</span></span>  
 [<span data-ttu-id="659fc-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="659fc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
