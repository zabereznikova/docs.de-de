---
title: StackOverflowInfo-Struktur
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1e652588d27521a04015228e86eb9af9c53346e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440813"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="c3a11-102">StackOverflowInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="c3a11-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="c3a11-103">Speichert den Typ des aufgetretenen Überlaufs und Informationen für die Ausnahme, die aufgrund eines Überlaufs in der ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="c3a11-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3a11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3a11-104">Syntax</span></span>  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="c3a11-105">Member</span><span class="sxs-lookup"><span data-stu-id="c3a11-105">Members</span></span>  
  
|<span data-ttu-id="c3a11-106">Member</span><span class="sxs-lookup"><span data-stu-id="c3a11-106">Member</span></span>|<span data-ttu-id="c3a11-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3a11-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="c3a11-108">Der Wert der [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) -Enumeration, der den Typ des Überlaufs angibt.</span><span class="sxs-lookup"><span data-stu-id="c3a11-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="c3a11-109">Ein Zeiger auf eine Win32- `EXCEPTION_POINTERS` Objekt, das einen Ausnahmedatensatz mit eine computerunabhängige Beschreibung einer Ausnahme und einen Kontextdatensatz mit einer Beschreibung rechnerabhängige des Kontexts Prozessor zum Zeitpunkt der Ausnahme enthält.</span><span class="sxs-lookup"><span data-stu-id="c3a11-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3a11-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3a11-110">Remarks</span></span>  
 <span data-ttu-id="c3a11-111">Ein `StackOverflowInfo` Objekt wird zum Übergeben der [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) Methode zum `Event_StackOverflow` Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="c3a11-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3a11-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3a11-112">Requirements</span></span>  
 <span data-ttu-id="c3a11-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3a11-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3a11-114">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="c3a11-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c3a11-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c3a11-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3a11-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3a11-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a11-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3a11-117">See Also</span></span>  
 [<span data-ttu-id="c3a11-118">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c3a11-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
