---
title: StackOverflowType-Enumeration
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c9119a2b842a0efcd4af752ba72dbfda03bf13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653859"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="bc0bf-102">StackOverflowType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bc0bf-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="bc0bf-103">Enthält Werte, die angeben, die zugrunde liegende Ursache für ein Stack Overflow-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bc0bf-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc0bf-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="bc0bf-105">Member</span><span class="sxs-lookup"><span data-stu-id="bc0bf-105">Members</span></span>  
  
|<span data-ttu-id="bc0bf-106">Member</span><span class="sxs-lookup"><span data-stu-id="bc0bf-106">Member</span></span>|<span data-ttu-id="bc0bf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc0bf-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="bc0bf-108">Der Stapelüberlauf wurde durch die ausführungs-Engine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="bc0bf-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="bc0bf-109">Der Stapelüberlauf verursachte von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="bc0bf-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="bc0bf-110">Der Stapelüberlauf verursachte von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="bc0bf-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc0bf-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc0bf-111">Remarks</span></span>  
 <span data-ttu-id="bc0bf-112">Diese Informationen werden an den Host übergeben, durch einen Aufruf der [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="bc0bf-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc0bf-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc0bf-113">Requirements</span></span>  
 <span data-ttu-id="bc0bf-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc0bf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc0bf-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bc0bf-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc0bf-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc0bf-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc0bf-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc0bf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0bf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc0bf-118">See also</span></span>
- [<span data-ttu-id="bc0bf-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="bc0bf-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
