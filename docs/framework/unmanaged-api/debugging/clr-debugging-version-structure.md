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
ms.openlocfilehash: 651b916a0e3ca178432094428611f9bcc8f0fd17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132420"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="d49be-102">CLR_DEBUGGING_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="d49be-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="d49be-103">Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.</span><span class="sxs-lookup"><span data-stu-id="d49be-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d49be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d49be-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d49be-105">Member</span><span class="sxs-lookup"><span data-stu-id="d49be-105">Members</span></span>  
  
|<span data-ttu-id="d49be-106">Member</span><span class="sxs-lookup"><span data-stu-id="d49be-106">Member</span></span>|<span data-ttu-id="d49be-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d49be-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="d49be-108">Die Versionsnummer der-Struktur.</span><span class="sxs-lookup"><span data-stu-id="d49be-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="d49be-109">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="d49be-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="d49be-110">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="d49be-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="d49be-111">Die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="d49be-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="d49be-112">Die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="d49be-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d49be-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d49be-113">Remarks</span></span>  
 <span data-ttu-id="d49be-114">Die `CLR_DEBUGGING_VERSION`-Struktur ist identisch mit der COR_VERSION-Struktur. die `CLR_DEBUGGING_VERSION` Struktur bietet jedoch ein zusätzliches Struktur Versions Feld (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="d49be-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="d49be-115">Dieses Feld muss derzeit auf 0 (null) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d49be-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d49be-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d49be-116">Requirements</span></span>  
 <span data-ttu-id="d49be-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d49be-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d49be-118">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="d49be-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d49be-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d49be-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d49be-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d49be-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d49be-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d49be-121">See also</span></span>

- [<span data-ttu-id="d49be-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="d49be-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d49be-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d49be-123">Debugging</span></span>](index.md)
