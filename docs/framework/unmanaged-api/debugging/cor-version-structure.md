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
ms.openlocfilehash: e2668e36debebb5ba71277912f37833eba584fde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403278"
---
# <a name="corversion-structure"></a><span data-ttu-id="48688-102">COR_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="48688-102">COR_VERSION Structure</span></span>
<span data-ttu-id="48688-103">Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="48688-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48688-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48688-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="48688-105">Member</span><span class="sxs-lookup"><span data-stu-id="48688-105">Members</span></span>  
  
|<span data-ttu-id="48688-106">Member</span><span class="sxs-lookup"><span data-stu-id="48688-106">Member</span></span>|<span data-ttu-id="48688-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48688-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="48688-108">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="48688-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="48688-109">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="48688-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="48688-110">Die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="48688-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="48688-111">Sub-Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="48688-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48688-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48688-112">Remarks</span></span>  
 <span data-ttu-id="48688-113">Ist die Versionsnummer 1.0.3705.288, 1 ist die Hauptversionsnummer, 0 ist die Nummer der Nebenversion 3705 wird die Buildnummer und 288 ist das Sub-Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="48688-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48688-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48688-114">Requirements</span></span>  
 <span data-ttu-id="48688-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48688-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48688-116">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="48688-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="48688-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48688-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48688-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48688-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48688-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48688-119">See Also</span></span>  
 [<span data-ttu-id="48688-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="48688-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="48688-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="48688-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
