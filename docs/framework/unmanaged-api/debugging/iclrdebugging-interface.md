---
title: ICLRDebugging-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793631"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="4f244-102">ICLRDebugging-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f244-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="4f244-103">Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.</span><span class="sxs-lookup"><span data-stu-id="4f244-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f244-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4f244-104">Methods</span></span>  
  
|<span data-ttu-id="4f244-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="4f244-105">Method</span></span>|<span data-ttu-id="4f244-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f244-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f244-107">OpenVirtualProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="4f244-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="4f244-108">Ruft die ICorDebugProcess-Schnittstelle ab, die einem Common Language Runtime (CLR)-Modul entspricht, das in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4f244-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="4f244-109">CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="4f244-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="4f244-110">Bestimmt, ob eine Bibliothek, die von einer [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle bereitgestellt wurde, noch verwendet wird oder entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f244-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f244-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f244-111">Remarks</span></span>  
 <span data-ttu-id="4f244-112">Sie können eine Instanz der `ICLRDebugging`-Schnittstelle abrufen, indem Sie die [clrkreateinstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) -Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f244-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f244-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f244-113">Requirements</span></span>  
 <span data-ttu-id="4f244-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f244-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f244-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f244-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f244-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f244-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f244-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f244-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f244-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f244-118">See also</span></span>

- [<span data-ttu-id="4f244-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f244-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4f244-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4f244-120">Debugging</span></span>](index.md)
