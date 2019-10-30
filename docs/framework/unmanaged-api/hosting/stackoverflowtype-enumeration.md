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
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141470"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="ee3ed-102">StackOverflowType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ee3ed-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="ee3ed-103">Enthält Werte, die die zugrunde liegende Ursache eines Stapelüberlauf Ereignisses angeben.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee3ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee3ed-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="ee3ed-105">Member</span><span class="sxs-lookup"><span data-stu-id="ee3ed-105">Members</span></span>  
  
|<span data-ttu-id="ee3ed-106">Member</span><span class="sxs-lookup"><span data-stu-id="ee3ed-106">Member</span></span>|<span data-ttu-id="ee3ed-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee3ed-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="ee3ed-108">Der Stapelüberlauf wurde von der Ausführungs-Engine verursacht.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="ee3ed-109">Der Stapelüberlauf wurde durch verwalteten Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="ee3ed-110">Der Stapelüberlauf wurde durch nicht verwalteten Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee3ed-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee3ed-111">Remarks</span></span>  
 <span data-ttu-id="ee3ed-112">Diese Informationen werden an den Host über einen aufzurufenden Befehl der [iaktiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) -Methode übermittelt.</span><span class="sxs-lookup"><span data-stu-id="ee3ed-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee3ed-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee3ed-113">Requirements</span></span>  
 <span data-ttu-id="ee3ed-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee3ed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee3ed-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ee3ed-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee3ed-116">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ee3ed-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee3ed-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee3ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee3ed-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee3ed-118">See also</span></span>

- [<span data-ttu-id="ee3ed-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ee3ed-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
