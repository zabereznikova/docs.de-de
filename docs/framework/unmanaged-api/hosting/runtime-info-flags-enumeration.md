---
title: RUNTIME_INFO_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09bd32172bcad298eebc2921461fdc953e9c6d6e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468292"
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="ad707-102">RUNTIME_INFO_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ad707-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="ad707-103">Enthält Werte, die angeben, welche Informationen über die common Language Runtime (CLR) zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ad707-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad707-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad707-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="ad707-105">Member</span><span class="sxs-lookup"><span data-stu-id="ad707-105">Members</span></span>  
  
|<span data-ttu-id="ad707-106">Member</span><span class="sxs-lookup"><span data-stu-id="ad707-106">Member</span></span>|<span data-ttu-id="ad707-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad707-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="ad707-108">Gibt an, dass Verzeichnisinformationen nicht enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="ad707-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="ad707-109">Gibt an, dass keine Informationen zur Version enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="ad707-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="ad707-110">Gibt an, dass ein Fehlerdialogfeld bei einem Fehler nicht angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad707-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="ad707-111">Gibt an, dass die Auswirkungen des Aufrufs der [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) Funktion mit dem SEM_FAILCRITICALERRORS-Flag überschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad707-111">Indicates that the effects of calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="ad707-112">D. h. soll ein Dialogfeld für die Installation bei einem Fehler unterdrückt wird angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ad707-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="ad707-113">Gibt eine Anforderung für Informationen zu einer AMD-64-kompatible Version der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="ad707-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="ad707-114">Gibt eine Anforderung für Informationen zu einer IA-64-kompatible Version der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="ad707-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="ad707-115">Gibt eine Anforderung für Informationen zu einer X86 kompatible Version der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="ad707-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="ad707-116">Gibt an, dass das Upgrade Versionsinformationen eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ad707-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad707-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad707-117">Remarks</span></span>  
 <span data-ttu-id="ad707-118">Die folgenden Flags der Plattform-Architektur können angegebenen nur jeweils nur ein und können nicht kombiniert werden:</span><span class="sxs-lookup"><span data-stu-id="ad707-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="ad707-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="ad707-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="ad707-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="ad707-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="ad707-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="ad707-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad707-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad707-122">Requirements</span></span>  
 <span data-ttu-id="ad707-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad707-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad707-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ad707-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad707-125">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="ad707-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad707-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad707-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad707-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad707-127">See Also</span></span>  
 [<span data-ttu-id="ad707-128">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ad707-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
