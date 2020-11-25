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
ms.openlocfilehash: 31640ada28af8e35554b91d5931d427fbaa8dcbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721854"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="de457-102">HOST_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="de457-102">HOST_TYPE Enumeration</span></span>

<span data-ttu-id="de457-103">Enthält Werte, die den Typ des Hosts angeben, von dem eine Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="de457-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de457-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de457-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="de457-105">Member</span><span class="sxs-lookup"><span data-stu-id="de457-105">Members</span></span>  
  
|<span data-ttu-id="de457-106">Member</span><span class="sxs-lookup"><span data-stu-id="de457-106">Member</span></span>|<span data-ttu-id="de457-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="de457-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="de457-108">Starten Sie die Anwendung aus AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="de457-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="de457-109">Verwenden Sie diesen Wert für teilweise vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="de457-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="de457-110">Starten Sie die Anwendung direkt.</span><span class="sxs-lookup"><span data-stu-id="de457-110">Launch the application directly.</span></span> <span data-ttu-id="de457-111">Das heißt, Sie starten die Anwendung aus ihrer eigenen exe-Datei.</span><span class="sxs-lookup"><span data-stu-id="de457-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="de457-112">Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="de457-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="de457-113">Identisch mit HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="de457-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de457-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="de457-114">Requirements</span></span>  

 <span data-ttu-id="de457-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de457-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de457-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="de457-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de457-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de457-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de457-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de457-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de457-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de457-119">See also</span></span>

- [<span data-ttu-id="de457-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="de457-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
