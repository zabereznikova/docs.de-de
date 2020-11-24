---
title: CorNativeLinkFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: ef9b177bee0651b6b8ea994610315ce93524e8e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676932"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="47efd-102">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="47efd-102">CorNativeLinkFlags Enumeration</span></span>

<span data-ttu-id="47efd-103">Stellt Flagwerte bereit, die beim Verknüpfen von nativem Code vom Linker verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47efd-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47efd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47efd-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="47efd-105">Member</span><span class="sxs-lookup"><span data-stu-id="47efd-105">Members</span></span>  
  
|<span data-ttu-id="47efd-106">Member</span><span class="sxs-lookup"><span data-stu-id="47efd-106">Member</span></span>|<span data-ttu-id="47efd-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="47efd-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="47efd-108">Gibt keine Flags an.</span><span class="sxs-lookup"><span data-stu-id="47efd-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="47efd-109">Gibt ein `setLastError` Schlüsselwort an.</span><span class="sxs-lookup"><span data-stu-id="47efd-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="47efd-110">Gibt ein `nomangle` Schlüsselwort an.</span><span class="sxs-lookup"><span data-stu-id="47efd-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="47efd-111">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="47efd-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47efd-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="47efd-112">Requirements</span></span>  

 <span data-ttu-id="47efd-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47efd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47efd-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="47efd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47efd-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="47efd-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47efd-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47efd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47efd-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47efd-117">See also</span></span>

- [<span data-ttu-id="47efd-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="47efd-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
