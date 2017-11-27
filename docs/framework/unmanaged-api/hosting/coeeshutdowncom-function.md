---
title: CoEEShutDownCOM-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d6d9e3d650f65ef084c63104980bca0ac77f1bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="85a66-102">CoEEShutDownCOM-Funktion</span><span class="sxs-lookup"><span data-stu-id="85a66-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="85a66-103">Erzwingt, dass die common Language Runtime (CLR), alle Schnittstellenzeiger freizugeben, die sie innerhalb der Runtime callable Wrappern (RCW) enthält.</span><span class="sxs-lookup"><span data-stu-id="85a66-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="85a66-104">Dies hat den Effekt des Freigebens von allen RCW-Caches.</span><span class="sxs-lookup"><span data-stu-id="85a66-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="85a66-105">Diese globale Funktion ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85a66-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="85a66-106">Verwenden Sie stattdessen den Einstiegspunkt für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="85a66-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a66-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="85a66-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="85a66-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85a66-108">Remarks</span></span>  
 <span data-ttu-id="85a66-109">Die `CoEEShutDownCOM` Funktion zuerst die RCWs in allen Kontexten und in allen Caches frei und entfernt dann Löschvorgänge Benachrichtigungen im Setup vorhanden.</span><span class="sxs-lookup"><span data-stu-id="85a66-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="85a66-110">Keine DLL entladen auftritt.</span><span class="sxs-lookup"><span data-stu-id="85a66-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="85a66-111">Diese Funktion wirkt sich auf alle Laufzeiten, die in den Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="85a66-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="85a66-112">Beginnend mit der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], rufen Sie den Einstiegspunkt für diese Funktion auf die bestimmte Laufzeit gelten soll.</span><span class="sxs-lookup"><span data-stu-id="85a66-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="85a66-113">Rufen Sie zum Abrufen des Einstiegspunkts der [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) Methode, und geben Sie "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="85a66-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85a66-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85a66-114">Requirements</span></span>  
 <span data-ttu-id="85a66-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85a66-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85a66-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85a66-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85a66-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="85a66-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85a66-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85a66-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a66-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85a66-119">See Also</span></span>  
 [<span data-ttu-id="85a66-120">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="85a66-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
