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
ms.openlocfilehash: 8541ea7b614ff4a6ca666f0e2549a7f50e190192
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135875"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="cd01f-102">StackOverflowType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cd01f-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="cd01f-103">Enthält Werte, die angeben, die zugrunde liegende Ursache für ein Stack Overflow-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="cd01f-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd01f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd01f-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="cd01f-105">Member</span><span class="sxs-lookup"><span data-stu-id="cd01f-105">Members</span></span>  
  
|<span data-ttu-id="cd01f-106">Member</span><span class="sxs-lookup"><span data-stu-id="cd01f-106">Member</span></span>|<span data-ttu-id="cd01f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd01f-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="cd01f-108">Der Stapelüberlauf wurde durch die ausführungs-Engine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cd01f-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="cd01f-109">Der Stapelüberlauf verursachte von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="cd01f-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="cd01f-110">Der Stapelüberlauf verursachte von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="cd01f-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd01f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd01f-111">Remarks</span></span>  
 <span data-ttu-id="cd01f-112">Diese Informationen werden an den Host übergeben, durch einen Aufruf der [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="cd01f-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd01f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd01f-113">Requirements</span></span>  
 <span data-ttu-id="cd01f-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd01f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd01f-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd01f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd01f-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd01f-116">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cd01f-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cd01f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd01f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd01f-118">See also</span></span>

- [<span data-ttu-id="cd01f-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="cd01f-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
