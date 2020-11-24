---
title: ICorDebugProcess3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
ms.openlocfilehash: ef8dbd5253c02355f85fba626fa7e68ed62df4bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686442"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="b7dcf-102">ICorDebugProcess3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7dcf-102">ICorDebugProcess3 Interface</span></span>

<span data-ttu-id="b7dcf-103">Steuert benutzerdefinierte Debuggerbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="b7dcf-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7dcf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b7dcf-104">Methods</span></span>  
  
|<span data-ttu-id="b7dcf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b7dcf-105">Method</span></span>|<span data-ttu-id="b7dcf-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b7dcf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7dcf-107">SetEnableCustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="b7dcf-107">SetEnableCustomNotification Method</span></span>](icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="b7dcf-108">Aktiviert und deaktiviert benutzerdefinierte Debugger-Benachrichtigungen vom angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="b7dcf-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7dcf-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7dcf-109">Remarks</span></span>  

 <span data-ttu-id="b7dcf-110">Diese Schnittstelle erweitert logisch die ICorDebugProcess-und ICorDebugProcess2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b7dcf-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7dcf-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b7dcf-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7dcf-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b7dcf-112">Requirements</span></span>  

 <span data-ttu-id="b7dcf-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7dcf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7dcf-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7dcf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7dcf-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7dcf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7dcf-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7dcf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7dcf-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7dcf-117">See also</span></span>

- [<span data-ttu-id="b7dcf-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b7dcf-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b7dcf-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b7dcf-119">Debugging</span></span>](index.md)
