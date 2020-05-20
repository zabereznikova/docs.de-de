---
title: HOST_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: e8dda83df8a320733f45dbcc13599cdf37d26492
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617151"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="fa6db-102">HOST_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fa6db-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="fa6db-103">Enthält Werte, die den Typ des Hosts angeben, von dem eine Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="fa6db-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa6db-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="fa6db-105">Member</span><span class="sxs-lookup"><span data-stu-id="fa6db-105">Members</span></span>  
  
|<span data-ttu-id="fa6db-106">Member</span><span class="sxs-lookup"><span data-stu-id="fa6db-106">Member</span></span>|<span data-ttu-id="fa6db-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa6db-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="fa6db-108">Starten Sie die Anwendung aus "AppLaunch. exe".</span><span class="sxs-lookup"><span data-stu-id="fa6db-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="fa6db-109">Verwenden Sie diesen Wert für teilweise vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fa6db-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="fa6db-110">Starten Sie die Anwendung direkt.</span><span class="sxs-lookup"><span data-stu-id="fa6db-110">Launch the application directly.</span></span> <span data-ttu-id="fa6db-111">Das heißt, Sie starten die Anwendung aus ihrer eigenen exe-Datei.</span><span class="sxs-lookup"><span data-stu-id="fa6db-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="fa6db-112">Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fa6db-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="fa6db-113">Identisch mit HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="fa6db-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa6db-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa6db-114">Requirements</span></span>  
 <span data-ttu-id="fa6db-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa6db-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6db-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fa6db-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa6db-117">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fa6db-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa6db-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa6db-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6db-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa6db-119">See also</span></span>

- [<span data-ttu-id="fa6db-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fa6db-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
