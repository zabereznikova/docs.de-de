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
ms.openlocfilehash: 9211af4726617598f3dd8772383cade6368e6c08
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007623"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="bea1d-102">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bea1d-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="bea1d-103">Stellt Flagwerte bereit, die beim Verknüpfen von nativem Code vom Linker verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bea1d-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bea1d-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="bea1d-105">Member</span><span class="sxs-lookup"><span data-stu-id="bea1d-105">Members</span></span>  
  
|<span data-ttu-id="bea1d-106">Member</span><span class="sxs-lookup"><span data-stu-id="bea1d-106">Member</span></span>|<span data-ttu-id="bea1d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bea1d-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="bea1d-108">Gibt keine Flags an.</span><span class="sxs-lookup"><span data-stu-id="bea1d-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="bea1d-109">Gibt ein `setLastError` Schlüsselwort an.</span><span class="sxs-lookup"><span data-stu-id="bea1d-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="bea1d-110">Gibt ein `nomangle` Schlüsselwort an.</span><span class="sxs-lookup"><span data-stu-id="bea1d-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="bea1d-111">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="bea1d-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bea1d-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bea1d-112">Requirements</span></span>  
 <span data-ttu-id="bea1d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bea1d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea1d-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bea1d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bea1d-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bea1d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bea1d-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea1d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea1d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bea1d-117">See also</span></span>

- [<span data-ttu-id="bea1d-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="bea1d-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
