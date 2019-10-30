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
ms.openlocfilehash: cc0cea10b4a209583fb7afb551a6b80d52ad7f62
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127026"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="a275c-102">HOST_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a275c-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="a275c-103">Enthält Werte, die den Typ des Hosts angeben, von dem eine Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a275c-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a275c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a275c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a275c-105">Member</span><span class="sxs-lookup"><span data-stu-id="a275c-105">Members</span></span>  
  
|<span data-ttu-id="a275c-106">Member</span><span class="sxs-lookup"><span data-stu-id="a275c-106">Member</span></span>|<span data-ttu-id="a275c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a275c-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="a275c-108">Starten Sie die Anwendung aus "AppLaunch. exe".</span><span class="sxs-lookup"><span data-stu-id="a275c-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="a275c-109">Verwenden Sie diesen Wert für teilweise vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="a275c-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="a275c-110">Starten Sie die Anwendung direkt.</span><span class="sxs-lookup"><span data-stu-id="a275c-110">Launch the application directly.</span></span> <span data-ttu-id="a275c-111">Das heißt, Sie starten die Anwendung aus ihrer eigenen exe-Datei.</span><span class="sxs-lookup"><span data-stu-id="a275c-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="a275c-112">Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="a275c-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="a275c-113">Identisch mit HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="a275c-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a275c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a275c-114">Requirements</span></span>  
 <span data-ttu-id="a275c-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a275c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a275c-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a275c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a275c-117">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a275c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a275c-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a275c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a275c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a275c-119">See also</span></span>

- [<span data-ttu-id="a275c-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a275c-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
