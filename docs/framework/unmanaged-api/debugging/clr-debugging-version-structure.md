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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87f938a7119abe4a88da65bd779a5f4a02499516
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117117"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="388e5-102">CLR_DEBUGGING_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="388e5-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="388e5-103">Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.</span><span class="sxs-lookup"><span data-stu-id="388e5-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="388e5-104">Syntax</span></span>  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="388e5-105">Member</span><span class="sxs-lookup"><span data-stu-id="388e5-105">Members</span></span>  
  
|<span data-ttu-id="388e5-106">Member</span><span class="sxs-lookup"><span data-stu-id="388e5-106">Member</span></span>|<span data-ttu-id="388e5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="388e5-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="388e5-108">Die Versionsnummer der Struktur</span><span class="sxs-lookup"><span data-stu-id="388e5-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="388e5-109">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="388e5-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="388e5-110">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="388e5-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="388e5-111">Die Nummer des Builds.</span><span class="sxs-lookup"><span data-stu-id="388e5-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="388e5-112">Die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="388e5-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="388e5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="388e5-113">Remarks</span></span>  
 <span data-ttu-id="388e5-114">Die `CLR_DEBUGGING_VERSION` hat die gleiche Struktur wie COR_VERSION-Struktur, jedoch die `CLR_DEBUGGING_VERSION` Struktur bietet eine zusätzliche Strukturversionsfeld (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="388e5-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="388e5-115">Derzeit muss dieses Feld auf NULL festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="388e5-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="388e5-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="388e5-116">Requirements</span></span>  
 <span data-ttu-id="388e5-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="388e5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="388e5-118">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="388e5-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="388e5-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="388e5-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="388e5-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="388e5-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="388e5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="388e5-121">See also</span></span>

- [<span data-ttu-id="388e5-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="388e5-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="388e5-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="388e5-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
