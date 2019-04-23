---
title: COR_VERSION-Struktur
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00e58d83c19c3cb6a2e1eb38942500d7f5dc5cf9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118923"
---
# <a name="corversion-structure"></a><span data-ttu-id="68fd7-102">COR_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="68fd7-102">COR_VERSION Structure</span></span>
<span data-ttu-id="68fd7-103">Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="68fd7-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68fd7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68fd7-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="68fd7-105">Member</span><span class="sxs-lookup"><span data-stu-id="68fd7-105">Members</span></span>  
  
|<span data-ttu-id="68fd7-106">Member</span><span class="sxs-lookup"><span data-stu-id="68fd7-106">Member</span></span>|<span data-ttu-id="68fd7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68fd7-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="68fd7-108">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="68fd7-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="68fd7-109">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="68fd7-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="68fd7-110">Die Nummer des Builds.</span><span class="sxs-lookup"><span data-stu-id="68fd7-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="68fd7-111">Die untergeordnete Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="68fd7-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68fd7-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68fd7-112">Remarks</span></span>  
 <span data-ttu-id="68fd7-113">Ist die Versionsnummer 1.0.3705.288, 1 ist die Hauptversionsnummer, 0 ist die Nummer der Nebenversion, 3705 ist die Nummer des Builds und 288 ist das Sub-Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="68fd7-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68fd7-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68fd7-114">Requirements</span></span>  
 <span data-ttu-id="68fd7-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68fd7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68fd7-116">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="68fd7-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="68fd7-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68fd7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68fd7-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68fd7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fd7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68fd7-119">See also</span></span>

- [<span data-ttu-id="68fd7-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="68fd7-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="68fd7-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="68fd7-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
