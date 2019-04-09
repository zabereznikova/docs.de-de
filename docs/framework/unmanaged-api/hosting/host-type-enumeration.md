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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfb1cff3e95c5ff86d22913745b7d14982766b48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175226"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="b4d5f-102">HOST_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b4d5f-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="b4d5f-103">Enthält Werte, die den Typ des Hosts angeben, die eine Anwendung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b4d5f-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4d5f-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="b4d5f-105">Member</span><span class="sxs-lookup"><span data-stu-id="b4d5f-105">Members</span></span>  
  
|<span data-ttu-id="b4d5f-106">Member</span><span class="sxs-lookup"><span data-stu-id="b4d5f-106">Member</span></span>|<span data-ttu-id="b4d5f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4d5f-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="b4d5f-108">Starten Sie die Anwendung über AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="b4d5f-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="b4d5f-109">Verwenden Sie diesen Wert für teilweise vertrauenswürdigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b4d5f-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="b4d5f-110">Starten Sie die Anwendung direkt auf.</span><span class="sxs-lookup"><span data-stu-id="b4d5f-110">Launch the application directly.</span></span> <span data-ttu-id="b4d5f-111">Starten Sie die Anwendung über einen eigenen .exe-Datei, also.</span><span class="sxs-lookup"><span data-stu-id="b4d5f-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="b4d5f-112">Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b4d5f-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="b4d5f-113">Same as HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="b4d5f-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4d5f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4d5f-114">Requirements</span></span>  
 <span data-ttu-id="b4d5f-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4d5f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d5f-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4d5f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4d5f-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4d5f-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b4d5f-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b4d5f-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4d5f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4d5f-119">See also</span></span>

- [<span data-ttu-id="b4d5f-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b4d5f-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
