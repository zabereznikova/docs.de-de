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
ms.openlocfilehash: 6f4fbb40053628d60ba7f094fcb5d50a94d63e1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729940"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="d2229-102">RUNTIME_INFO_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2229-102">RUNTIME_INFO_FLAGS Enumeration</span></span>

<span data-ttu-id="d2229-103">Enthält Werte, die angeben, welche Informationen zum Common Language Runtime (CLR) zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2229-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2229-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2229-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="d2229-105">Member</span><span class="sxs-lookup"><span data-stu-id="d2229-105">Members</span></span>  
  
|<span data-ttu-id="d2229-106">Member</span><span class="sxs-lookup"><span data-stu-id="d2229-106">Member</span></span>|<span data-ttu-id="d2229-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d2229-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="d2229-108">Gibt an, dass Verzeichnisinformationen nicht eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2229-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="d2229-109">Gibt an, dass keine Versionsinformationen eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2229-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="d2229-110">Gibt an, dass ein Fehler Dialogfeld bei einem Fehler nicht angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2229-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="d2229-111">Gibt an, dass die Auswirkungen des Aufrufs der [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) -Funktion mit dem SEM_FAILCRITICALERRORS-Flag überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2229-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="d2229-112">Das heißt, ein Installations Dialogfeld sollte bei einem Fehler angezeigt werden, anstatt unterdrückt zu werden.</span><span class="sxs-lookup"><span data-stu-id="d2229-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="d2229-113">Gibt eine Anforderung von Informationen über eine mit AMD 64 kompatible Version der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="d2229-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="d2229-114">Gibt eine Anforderung von Informationen über eine IA-64-kompatible Version der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="d2229-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="d2229-115">Gibt eine Anforderung von Informationen über eine x86-kompatible Version der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="d2229-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="d2229-116">Gibt an, dass Informationen zur Versions Aktualisierung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2229-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2229-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2229-117">Remarks</span></span>  

 <span data-ttu-id="d2229-118">Die folgenden Plattformarchitektur-Flags können jeweils nur einzeln angegeben werden und können nicht kombiniert werden:</span><span class="sxs-lookup"><span data-stu-id="d2229-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="d2229-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="d2229-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="d2229-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="d2229-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="d2229-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="d2229-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2229-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d2229-122">Requirements</span></span>  

 <span data-ttu-id="d2229-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2229-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2229-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d2229-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2229-125">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2229-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2229-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2229-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2229-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2229-127">See also</span></span>

- [<span data-ttu-id="d2229-128">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d2229-128">Hosting Enumerations</span></span>](hosting-enumerations.md)
