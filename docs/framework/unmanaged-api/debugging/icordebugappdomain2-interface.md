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
ms.openlocfilehash: bff270ff774692d058a36c7f47ab474b08bceb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088961"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="ad226-102">ICorDebugAppDomain2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad226-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="ad226-103">Stellt Methoden bereit, um mit Arrays, Zeigern, Funktions Zeigern und Verweis Typen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad226-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="ad226-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ad226-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad226-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ad226-105">Methods</span></span>  
  
|<span data-ttu-id="ad226-106">Methode</span><span class="sxs-lookup"><span data-stu-id="ad226-106">Method</span></span>|<span data-ttu-id="ad226-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad226-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad226-108">GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="ad226-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="ad226-109">Ruft ein Array vom angegebenen Typ oder einen Zeiger oder einen Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="ad226-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="ad226-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="ad226-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="ad226-111">Ruft einen Zeiger auf eine Funktion ab, die über eine angegebene Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="ad226-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad226-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad226-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad226-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ad226-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad226-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad226-114">Requirements</span></span>  
 <span data-ttu-id="ad226-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad226-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad226-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad226-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad226-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad226-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad226-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad226-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad226-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad226-119">See also</span></span>

- [<span data-ttu-id="ad226-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ad226-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
