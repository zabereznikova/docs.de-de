---
title: HOST_TYPE-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: HOST_TYPE
api_location: mscoree.dll
api_type: COM
f1_keywords: HOST_TYPE
helpviewer_keywords: HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e191293ff7bde6b1be2210af4e7830fec0d7290d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="f2203-102">HOST_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f2203-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="f2203-103">Enthält Werte, die den Typ des Hosts angeben, die eine Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="f2203-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2203-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2203-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="f2203-105">Member</span><span class="sxs-lookup"><span data-stu-id="f2203-105">Members</span></span>  
  
|<span data-ttu-id="f2203-106">Member</span><span class="sxs-lookup"><span data-stu-id="f2203-106">Member</span></span>|<span data-ttu-id="f2203-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2203-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="f2203-108">Starten Sie die Anwendung über AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="f2203-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="f2203-109">Verwenden Sie diesen Wert für teilweise vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f2203-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="f2203-110">Starten Sie die Anwendung direkt.</span><span class="sxs-lookup"><span data-stu-id="f2203-110">Launch the application directly.</span></span> <span data-ttu-id="f2203-111">D. h., starten Sie die Anwendung aus einer eigenen .exe-Datei.</span><span class="sxs-lookup"><span data-stu-id="f2203-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="f2203-112">Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f2203-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="f2203-113">Identisch mit HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="f2203-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2203-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2203-114">Requirements</span></span>  
 <span data-ttu-id="f2203-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2203-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2203-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2203-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2203-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="f2203-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2203-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2203-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2203-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2203-119">See Also</span></span>  
 [<span data-ttu-id="f2203-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f2203-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
