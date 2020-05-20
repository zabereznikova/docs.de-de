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
ms.openlocfilehash: 9b4c1187945b4c243375a3096c3a8a3b22599aef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616280"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="31f0f-102">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="31f0f-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="31f0f-103">Enthält Werte, die angeben, welche Elemente in eine benutzerdefinierte Teilmenge eines Heap Abbilds eingeschlossen werden sollen, wenn Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="31f0f-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f0f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31f0f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="31f0f-105">Member</span><span class="sxs-lookup"><span data-stu-id="31f0f-105">Members</span></span>  
  
|<span data-ttu-id="31f0f-106">Member</span><span class="sxs-lookup"><span data-stu-id="31f0f-106">Member</span></span>|<span data-ttu-id="31f0f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31f0f-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="31f0f-108">Gibt an, dass das benutzerdefinierte Heap Abbild als Minidump gestartet werden soll, und schließt zusätzliche Daten ein, die von den an dieselbe Methode übergebenen [CustomDumpItem](customdumpitem-structure.md) -Instanzen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31f0f-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="31f0f-109">Gibt an, dass das benutzerdefinierte Heap-Dump alle Lauf Zeit Zustandsdaten erfassen soll, die nicht dynamisch zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="31f0f-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31f0f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31f0f-110">Remarks</span></span>  
 <span data-ttu-id="31f0f-111">Ein Parameter vom Typ `ECustomDumpFlavor` wird an die [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="31f0f-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f0f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31f0f-112">Requirements</span></span>  
 <span data-ttu-id="31f0f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31f0f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f0f-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="31f0f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31f0f-115">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="31f0f-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31f0f-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f0f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f0f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31f0f-117">See also</span></span>

- [<span data-ttu-id="31f0f-118">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="31f0f-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="31f0f-119">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31f0f-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="31f0f-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="31f0f-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
