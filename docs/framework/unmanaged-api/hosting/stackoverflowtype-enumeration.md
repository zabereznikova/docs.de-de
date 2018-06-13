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
ms.openlocfilehash: 9e888b2359336c68ea6fdf52f798145fda12002e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440868"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="678fe-102">StackOverflowType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="678fe-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="678fe-103">Enthält Werte, die angeben, die Ursache eines Stack Overflow-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="678fe-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="678fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="678fe-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="678fe-105">Member</span><span class="sxs-lookup"><span data-stu-id="678fe-105">Members</span></span>  
  
|<span data-ttu-id="678fe-106">Member</span><span class="sxs-lookup"><span data-stu-id="678fe-106">Member</span></span>|<span data-ttu-id="678fe-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="678fe-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="678fe-108">Der Stapelüberlauf wurde durch das Ausführungsmodul verursacht.</span><span class="sxs-lookup"><span data-stu-id="678fe-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="678fe-109">Der Stapelüberlauf wurde von verwaltetem Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="678fe-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="678fe-110">Der Stapelüberlauf wurde von nicht verwaltetem Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="678fe-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="678fe-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="678fe-111">Remarks</span></span>  
 <span data-ttu-id="678fe-112">Diese Informationen werden an den Host übergeben, durch einen Aufruf der [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="678fe-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="678fe-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="678fe-113">Requirements</span></span>  
 <span data-ttu-id="678fe-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="678fe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="678fe-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="678fe-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="678fe-116">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="678fe-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="678fe-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="678fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678fe-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="678fe-118">See Also</span></span>  
 [<span data-ttu-id="678fe-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="678fe-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
