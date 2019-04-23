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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135875"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="ff7e3-102">StackOverflowType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ff7e3-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="ff7e3-103">Enthält Werte, die angeben, die zugrunde liegende Ursache für ein Stack Overflow-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ff7e3-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff7e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff7e3-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="ff7e3-105">Member</span><span class="sxs-lookup"><span data-stu-id="ff7e3-105">Members</span></span>  
  
|<span data-ttu-id="ff7e3-106">Member</span><span class="sxs-lookup"><span data-stu-id="ff7e3-106">Member</span></span>|<span data-ttu-id="ff7e3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff7e3-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="ff7e3-108">Der Stapelüberlauf wurde durch die ausführungs-Engine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ff7e3-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="ff7e3-109">Der Stapelüberlauf verursachte von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="ff7e3-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="ff7e3-110">Der Stapelüberlauf verursachte von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="ff7e3-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff7e3-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff7e3-111">Remarks</span></span>  
 <span data-ttu-id="ff7e3-112">Diese Informationen werden an den Host übergeben, durch einen Aufruf der [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ff7e3-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff7e3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff7e3-113">Requirements</span></span>  
 <span data-ttu-id="ff7e3-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff7e3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff7e3-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff7e3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff7e3-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff7e3-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff7e3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff7e3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff7e3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff7e3-118">See also</span></span>

- [<span data-ttu-id="ff7e3-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ff7e3-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
