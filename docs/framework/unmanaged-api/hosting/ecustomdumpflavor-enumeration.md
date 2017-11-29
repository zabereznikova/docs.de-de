---
title: ECustomDumpFlavor-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a7317a3a12acef2a16deebab9a1e1b10205ebf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="dd21e-102">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="dd21e-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="dd21e-103">Enthält Werte, die angeben, die eine benutzerdefinierte Teilmenge eines Heaps einzuschließenden Elemente zu speichern, beim Melden von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="dd21e-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd21e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd21e-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="dd21e-105">Member</span><span class="sxs-lookup"><span data-stu-id="dd21e-105">Members</span></span>  
  
|<span data-ttu-id="dd21e-106">Member</span><span class="sxs-lookup"><span data-stu-id="dd21e-106">Member</span></span>|<span data-ttu-id="dd21e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd21e-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="dd21e-108">Gibt an, dass das benutzerdefinierte Heap Speicherabbild als Minidumps gestartet und zusätzliche Daten, die von einer angegebenen eingeschlossen werden sollen [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) Instanzen derselben Methode zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="dd21e-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="dd21e-109">Gibt an, dass das benutzerdefinierte Heap Speicherabbild alle Laufzeitzustand Daten sammelt, die nicht dynamisch zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="dd21e-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd21e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd21e-110">Remarks</span></span>  
 <span data-ttu-id="dd21e-111">Einen Parameter vom Typ `ECustomDumpFlavor` wird zum Übergeben der [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="dd21e-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd21e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd21e-112">Requirements</span></span>  
 <span data-ttu-id="dd21e-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd21e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd21e-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd21e-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd21e-115">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="dd21e-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd21e-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd21e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd21e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd21e-117">See Also</span></span>  
 [<span data-ttu-id="dd21e-118">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="dd21e-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="dd21e-119">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd21e-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="dd21e-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="dd21e-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
