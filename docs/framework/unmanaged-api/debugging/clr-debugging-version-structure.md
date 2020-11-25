---
title: CLR_DEBUGGING_VERSION-Struktur
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 8a2abe847728a2bb1f1345ef73e55b58e4704001
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729810"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="f817b-102">CLR_DEBUGGING_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="f817b-102">CLR_DEBUGGING_VERSION Structure</span></span>

<span data-ttu-id="f817b-103">Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.</span><span class="sxs-lookup"><span data-stu-id="f817b-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f817b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f817b-104">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="f817b-105">Member</span><span class="sxs-lookup"><span data-stu-id="f817b-105">Members</span></span>  
  
|<span data-ttu-id="f817b-106">Member</span><span class="sxs-lookup"><span data-stu-id="f817b-106">Member</span></span>|<span data-ttu-id="f817b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f817b-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="f817b-108">Die Versionsnummer der-Struktur.</span><span class="sxs-lookup"><span data-stu-id="f817b-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="f817b-109">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="f817b-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="f817b-110">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="f817b-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="f817b-111">Die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="f817b-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="f817b-112">Die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="f817b-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f817b-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f817b-113">Remarks</span></span>  

 <span data-ttu-id="f817b-114">Die- `CLR_DEBUGGING_VERSION` Struktur ist identisch mit der COR_VERSION-Struktur, aber die- `CLR_DEBUGGING_VERSION` Struktur stellt ein zusätzliches Struktur Versions Feld ( `wStructVersion` ) bereit.</span><span class="sxs-lookup"><span data-stu-id="f817b-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="f817b-115">Dieses Feld muss derzeit auf 0 (null) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f817b-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f817b-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f817b-116">Requirements</span></span>  

 <span data-ttu-id="f817b-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f817b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f817b-118">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="f817b-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="f817b-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f817b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f817b-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f817b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f817b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f817b-121">See also</span></span>

- [<span data-ttu-id="f817b-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="f817b-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="f817b-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f817b-123">Debugging</span></span>](index.md)
