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
ms.openlocfilehash: 5c6ef901f43cd6568f17657ed8e58bc2cc2cc0a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186055"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="6b780-102">ICorDebugAppDomain2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b780-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="6b780-103">Stellt Methoden zum Arbeiten mit Arrays, Zeigern, Funktionszeigern und Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="6b780-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="6b780-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6b780-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b780-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6b780-105">Methods</span></span>  
  
|<span data-ttu-id="6b780-106">Methode</span><span class="sxs-lookup"><span data-stu-id="6b780-106">Method</span></span>|<span data-ttu-id="6b780-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b780-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b780-108">GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="6b780-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="6b780-109">Ruft ein Array von den angegebenen Typ oder ein Zeiger oder Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="6b780-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="6b780-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="6b780-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="6b780-111">Ruft einen Zeiger auf eine Funktion, die einer bestimmten Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="6b780-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b780-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b780-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b780-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6b780-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b780-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b780-114">Requirements</span></span>  
 <span data-ttu-id="6b780-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b780-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b780-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b780-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b780-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b780-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b780-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b780-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b780-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b780-119">See also</span></span>

- [<span data-ttu-id="6b780-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6b780-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
