---
title: ECustomDumpFlavor-Enumeration
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2be9f112d5997ec8a6b126229eb8608eb8dd8520
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627641"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="8f506-102">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8f506-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="8f506-103">Enthält Werte, die angeben, die eine benutzerdefinierte Teilmenge eines Heaps einzuschließenden Elemente zu speichern, sollte ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="8f506-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f506-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f506-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="8f506-105">Member</span><span class="sxs-lookup"><span data-stu-id="8f506-105">Members</span></span>  
  
|<span data-ttu-id="8f506-106">Member</span><span class="sxs-lookup"><span data-stu-id="8f506-106">Member</span></span>|<span data-ttu-id="8f506-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f506-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="8f506-108">Gibt an, dass das benutzerdefinierte Heap-Speicherabbild sollte als Minidumps gestartet und zusätzliche Daten, die von einem angegebenen enthalten [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) Instanzen derselben Methode zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="8f506-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="8f506-109">Gibt an, dass das benutzerdefinierte Heap-Speicherabbild alle Laufzeitzustand Daten sammelt, die nicht dynamisch zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="8f506-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f506-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f506-110">Remarks</span></span>  
 <span data-ttu-id="8f506-111">Einen Parameter vom Typ `ECustomDumpFlavor` übergeben wird, um die [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="8f506-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f506-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f506-112">Requirements</span></span>  
 <span data-ttu-id="8f506-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f506-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f506-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f506-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f506-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f506-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f506-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f506-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f506-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f506-117">See also</span></span>
- [<span data-ttu-id="8f506-118">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8f506-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="8f506-119">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f506-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="8f506-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8f506-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
