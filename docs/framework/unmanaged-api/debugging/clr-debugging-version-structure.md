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
ms.openlocfilehash: 4be232ab557d582f3521b8775108c004b5a3dd78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403304"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="08678-102">CLR_DEBUGGING_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="08678-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="08678-103">Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.</span><span class="sxs-lookup"><span data-stu-id="08678-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08678-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08678-104">Syntax</span></span>  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="08678-105">Member</span><span class="sxs-lookup"><span data-stu-id="08678-105">Members</span></span>  
  
|<span data-ttu-id="08678-106">Member</span><span class="sxs-lookup"><span data-stu-id="08678-106">Member</span></span>|<span data-ttu-id="08678-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08678-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="08678-108">Die Versionsnummer der Struktur</span><span class="sxs-lookup"><span data-stu-id="08678-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="08678-109">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="08678-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="08678-110">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="08678-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="08678-111">Die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="08678-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="08678-112">Die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="08678-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08678-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08678-113">Remarks</span></span>  
 <span data-ttu-id="08678-114">Die `CLR_DEBUGGING_VERSION` Struktur ist identisch mit der COR_VERSION-Struktur, jedoch die `CLR_DEBUGGING_VERSION` Struktur bietet eine zusätzliche Version Strukturfeld (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="08678-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="08678-115">Derzeit muss dieses Feld auf NULL festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="08678-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08678-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08678-116">Requirements</span></span>  
 <span data-ttu-id="08678-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08678-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08678-118">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="08678-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="08678-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08678-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08678-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08678-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08678-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08678-121">See Also</span></span>  
 [<span data-ttu-id="08678-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="08678-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="08678-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="08678-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
