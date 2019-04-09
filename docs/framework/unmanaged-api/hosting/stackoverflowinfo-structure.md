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
ms.openlocfilehash: ac0f5d522a24394369583692f8c564254529bf13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137345"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="efa96-102">StackOverflowInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="efa96-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="efa96-103">Speichert den Typ der Überlauf, die aufgetreten sind und Informationen für die Ausnahme, die aufgrund der Überlauf ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="efa96-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa96-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efa96-104">Syntax</span></span>  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="efa96-105">Member</span><span class="sxs-lookup"><span data-stu-id="efa96-105">Members</span></span>  
  
|<span data-ttu-id="efa96-106">Member</span><span class="sxs-lookup"><span data-stu-id="efa96-106">Member</span></span>|<span data-ttu-id="efa96-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efa96-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="efa96-108">Der Wert der [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) -Enumeration, der den Typ des Überlaufs angibt.</span><span class="sxs-lookup"><span data-stu-id="efa96-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="efa96-109">Ein Zeiger auf eine Win32- `EXCEPTION_POINTERS` -Objekt, das einen Ausnahmedatensatz mit einer computerunabhängige Beschreibung einer Ausnahme und eines Kontextdatensatzes mit einer Beschreibung abhängig vom Computer des Kontexts Prozessor zum Zeitpunkt der Ausnahme enthält.</span><span class="sxs-lookup"><span data-stu-id="efa96-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efa96-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="efa96-110">Remarks</span></span>  
 <span data-ttu-id="efa96-111">Ein `StackOverflowInfo` Objekt wird zum Übergeben der [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) -Methode für `Event_StackOverflow` Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="efa96-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa96-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="efa96-112">Requirements</span></span>  
 <span data-ttu-id="efa96-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efa96-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa96-114">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="efa96-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="efa96-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="efa96-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="efa96-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="efa96-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efa96-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efa96-117">See also</span></span>

- [<span data-ttu-id="efa96-118">Hostingstrukturen</span><span class="sxs-lookup"><span data-stu-id="efa96-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
