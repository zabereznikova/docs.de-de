---
title: CoEEShutDownCOM-Funktion
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
ms.openlocfilehash: 774704698f92d546d6bafa61c65d18d083c65f89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716758"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="4b8bd-102">CoEEShutDownCOM-Funktion</span><span class="sxs-lookup"><span data-stu-id="4b8bd-102">CoEEShutDownCOM Function</span></span>

<span data-ttu-id="4b8bd-103">Erzwingt, dass der Common Language Runtime (CLR) alle Schnittstellen Zeiger freigibt, die er in Runtime Callable Wrapper (RCW) enthält.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="4b8bd-104">Dies hat den Effekt, dass alle RCW-Caches freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="4b8bd-105">Diese globale Funktion ist in der .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="4b8bd-106">Verwenden Sie stattdessen den Einstiegspunkt für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b8bd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b8bd-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4b8bd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b8bd-108">Remarks</span></span>  

 <span data-ttu-id="4b8bd-109">Die `CoEEShutDownCOM` Funktion gibt zuerst alle RCWs in allen Kontexten und in allen Caches frei und entfernt dann alle in Setup vorhandenen Lösch Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="4b8bd-110">Es erfolgt keine DLL-Entladung.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="4b8bd-111">Diese Funktion wirkt sich auf alle Laufzeiten aus, die in den Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="4b8bd-112">Beginnen Sie mit der .NET Framework 4, und nennen Sie den Einstiegspunkt für diese Funktion für die jeweilige Laufzeit, die Sie beeinflussen möchten.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="4b8bd-113">Um den Einstiegspunkt abzurufen, nennen Sie die [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) -Methode, und geben Sie "CoEEShutDownCOM" an.</span><span class="sxs-lookup"><span data-stu-id="4b8bd-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b8bd-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4b8bd-114">Requirements</span></span>  

 <span data-ttu-id="4b8bd-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b8bd-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b8bd-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4b8bd-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b8bd-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4b8bd-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b8bd-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b8bd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b8bd-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b8bd-119">See also</span></span>

- [<span data-ttu-id="4b8bd-120">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="4b8bd-120">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
