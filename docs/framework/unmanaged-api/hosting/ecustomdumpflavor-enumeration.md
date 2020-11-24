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
ms.openlocfilehash: 1b8440ed6e878aac3dd08d9f8ed528c93739a724
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686318"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="a5c38-102">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a5c38-102">ECustomDumpFlavor Enumeration</span></span>

<span data-ttu-id="a5c38-103">Enthält Werte, die angeben, welche Elemente in eine benutzerdefinierte Teilmenge eines Heap Abbilds eingeschlossen werden sollen, wenn Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="a5c38-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5c38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5c38-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="a5c38-105">Member</span><span class="sxs-lookup"><span data-stu-id="a5c38-105">Members</span></span>  
  
|<span data-ttu-id="a5c38-106">Member</span><span class="sxs-lookup"><span data-stu-id="a5c38-106">Member</span></span>|<span data-ttu-id="a5c38-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a5c38-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="a5c38-108">Gibt an, dass das benutzerdefinierte Heap Abbild als Minidump gestartet werden soll, und schließt zusätzliche Daten ein, die von den an dieselbe Methode übergebenen [CustomDumpItem](customdumpitem-structure.md) -Instanzen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5c38-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="a5c38-109">Gibt an, dass das benutzerdefinierte Heap-Dump alle Lauf Zeit Zustandsdaten erfassen soll, die nicht dynamisch zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="a5c38-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5c38-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5c38-110">Remarks</span></span>  

 <span data-ttu-id="a5c38-111">Ein Parameter vom Typ `ECustomDumpFlavor` wird an die [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="a5c38-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5c38-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a5c38-112">Requirements</span></span>  

 <span data-ttu-id="a5c38-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5c38-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5c38-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a5c38-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5c38-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5c38-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5c38-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5c38-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c38-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5c38-117">See also</span></span>

- [<span data-ttu-id="a5c38-118">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a5c38-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="a5c38-119">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5c38-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="a5c38-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a5c38-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
