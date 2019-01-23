---
title: ICorDebugAppDomain2-Schnittstelle1
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
ms.openlocfilehash: f4549b0fe6379979a7b9bd6344d65ff465f33f17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506133"
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="84e39-102">ICorDebugAppDomain2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="84e39-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="84e39-103">Stellt Methoden zum Arbeiten mit Arrays, Zeigern, Funktionszeigern und Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="84e39-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="84e39-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="84e39-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84e39-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="84e39-105">Methods</span></span>  
  
|<span data-ttu-id="84e39-106">Methode</span><span class="sxs-lookup"><span data-stu-id="84e39-106">Method</span></span>|<span data-ttu-id="84e39-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84e39-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84e39-108">GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="84e39-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="84e39-109">Ruft ein Array von den angegebenen Typ oder ein Zeiger oder Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="84e39-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="84e39-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="84e39-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="84e39-111">Ruft einen Zeiger auf eine Funktion, die einer bestimmten Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="84e39-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84e39-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84e39-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84e39-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="84e39-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e39-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84e39-114">Requirements</span></span>  
 <span data-ttu-id="84e39-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e39-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e39-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84e39-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84e39-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84e39-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84e39-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84e39-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e39-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e39-119">See also</span></span>
- [<span data-ttu-id="84e39-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="84e39-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
