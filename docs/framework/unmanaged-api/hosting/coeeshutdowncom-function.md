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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d990d63a007240ab0bd0240f7b45fed52e2a2129
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212247"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="67cbb-102">CoEEShutDownCOM-Funktion</span><span class="sxs-lookup"><span data-stu-id="67cbb-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="67cbb-103">Erzwingt die common Language Runtime (CLR), um alle Schnittstellenzeiger freizugeben, die sie in der Common Language Runtime callable Wrapper (RCW) enthält.</span><span class="sxs-lookup"><span data-stu-id="67cbb-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="67cbb-104">Dies hat den Effekt der Freigabe alle RCW-Caches.</span><span class="sxs-lookup"><span data-stu-id="67cbb-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="67cbb-105">Diese globale Funktion ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67cbb-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="67cbb-106">Verwenden Sie stattdessen den Einstiegspunkt für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="67cbb-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67cbb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="67cbb-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="67cbb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67cbb-108">Remarks</span></span>  
 <span data-ttu-id="67cbb-109">Die `CoEEShutDownCOM` Funktion gibt zuerst die RCWs in allen Kontexten und alle Caches frei, und entfernt dann alle Löschvorgänge-Benachrichtigung, die im Setup.</span><span class="sxs-lookup"><span data-stu-id="67cbb-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="67cbb-110">Tritt auf, keine DLL entladen.</span><span class="sxs-lookup"><span data-stu-id="67cbb-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="67cbb-111">Diese Funktion wirkt sich auf alle Laufzeiten, die in den Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="67cbb-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="67cbb-112">Beginnend mit der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], rufen Sie den Einstiegspunkt für diese Funktion auf die angegebene Runtime, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="67cbb-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="67cbb-113">Rufen Sie zum Abrufen des Einstiegspunkts der [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) Methode, und geben Sie "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="67cbb-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67cbb-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67cbb-114">Requirements</span></span>  
 <span data-ttu-id="67cbb-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67cbb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67cbb-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67cbb-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67cbb-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="67cbb-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67cbb-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67cbb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67cbb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67cbb-119">See also</span></span>
- [<span data-ttu-id="67cbb-120">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="67cbb-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
