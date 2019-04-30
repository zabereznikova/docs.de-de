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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968601"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="747b7-102">HOST_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="747b7-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="747b7-103">Enthält Werte, die den Typ des Hosts angeben, die eine Anwendung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="747b7-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="747b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="747b7-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="747b7-105">Member</span><span class="sxs-lookup"><span data-stu-id="747b7-105">Members</span></span>  
  
|<span data-ttu-id="747b7-106">Member</span><span class="sxs-lookup"><span data-stu-id="747b7-106">Member</span></span>|<span data-ttu-id="747b7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="747b7-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="747b7-108">Starten Sie die Anwendung über AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="747b7-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="747b7-109">Verwenden Sie diesen Wert für teilweise vertrauenswürdigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="747b7-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="747b7-110">Starten Sie die Anwendung direkt auf.</span><span class="sxs-lookup"><span data-stu-id="747b7-110">Launch the application directly.</span></span> <span data-ttu-id="747b7-111">Starten Sie die Anwendung über einen eigenen .exe-Datei, also.</span><span class="sxs-lookup"><span data-stu-id="747b7-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="747b7-112">Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="747b7-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="747b7-113">Same as HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="747b7-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="747b7-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="747b7-114">Requirements</span></span>  
 <span data-ttu-id="747b7-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="747b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="747b7-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="747b7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="747b7-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="747b7-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="747b7-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="747b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747b7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="747b7-119">See also</span></span>

- [<span data-ttu-id="747b7-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="747b7-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
