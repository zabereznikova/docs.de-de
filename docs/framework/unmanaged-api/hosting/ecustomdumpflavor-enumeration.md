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
ms.openlocfilehash: a416a51f5121f29d373fcfdfa6b0597d9b10ded5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779377"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="f9be9-102">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f9be9-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="f9be9-103">Enthält Werte, die angeben, die eine benutzerdefinierte Teilmenge eines Heaps einzuschließenden Elemente zu speichern, sollte ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="f9be9-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9be9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9be9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="f9be9-105">Member</span><span class="sxs-lookup"><span data-stu-id="f9be9-105">Members</span></span>  
  
|<span data-ttu-id="f9be9-106">Member</span><span class="sxs-lookup"><span data-stu-id="f9be9-106">Member</span></span>|<span data-ttu-id="f9be9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9be9-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="f9be9-108">Gibt an, dass das benutzerdefinierte Heap-Speicherabbild sollte als Minidumps gestartet und zusätzliche Daten, die von einem angegebenen enthalten [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) Instanzen derselben Methode zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f9be9-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="f9be9-109">Gibt an, dass das benutzerdefinierte Heap-Speicherabbild alle Laufzeitzustand Daten sammelt, die nicht dynamisch zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="f9be9-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9be9-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9be9-110">Remarks</span></span>  
 <span data-ttu-id="f9be9-111">Einen Parameter vom Typ `ECustomDumpFlavor` übergeben wird, um die [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f9be9-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9be9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9be9-112">Requirements</span></span>  
 <span data-ttu-id="f9be9-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9be9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9be9-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f9be9-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9be9-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9be9-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9be9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9be9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9be9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9be9-117">See also</span></span>

- [<span data-ttu-id="f9be9-118">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f9be9-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="f9be9-119">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9be9-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="f9be9-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f9be9-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
