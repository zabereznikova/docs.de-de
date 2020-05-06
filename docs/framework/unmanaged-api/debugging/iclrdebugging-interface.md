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
ms.openlocfilehash: a3d4297e3b16dd1637e6293dbf7f04d4fbeda50f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860383"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="f56f0-102">ICLRDebugging-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f56f0-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="f56f0-103">Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.</span><span class="sxs-lookup"><span data-stu-id="f56f0-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f56f0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f56f0-104">Methods</span></span>  
  
|<span data-ttu-id="f56f0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f56f0-105">Method</span></span>|<span data-ttu-id="f56f0-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f56f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f56f0-107">OpenVirtualProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="f56f0-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="f56f0-108">Ruft die ICorDebugProcess-Schnittstelle ab, die einem Common Language Runtime (CLR)-Modul entspricht, das in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f56f0-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="f56f0-109">CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="f56f0-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="f56f0-110">Bestimmt, ob eine Bibliothek, die von einer [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle bereitgestellt wurde, noch verwendet wird oder entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f56f0-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f56f0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f56f0-111">Remarks</span></span>  
 <span data-ttu-id="f56f0-112">Sie können eine Instanz der `ICLRDebugging` Schnittstelle abrufen, indem Sie die [clrkreateinstance](../hosting/clrcreateinstance-function.md) -Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="f56f0-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f56f0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f56f0-113">Requirements</span></span>  
 <span data-ttu-id="f56f0-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f56f0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f56f0-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f56f0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f56f0-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f56f0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f56f0-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f56f0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f56f0-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f56f0-118">See also</span></span>

- [<span data-ttu-id="f56f0-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f56f0-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f56f0-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f56f0-120">Debugging</span></span>](index.md)
