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
ms.openlocfilehash: b1f0a36d186c6d9788d43b075bf9d67c36ed1acb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740571"
---
# <a name="corversion-structure"></a><span data-ttu-id="d9b59-102">COR_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="d9b59-102">COR_VERSION Structure</span></span>
<span data-ttu-id="d9b59-103">Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d9b59-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9b59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9b59-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="d9b59-105">Member</span><span class="sxs-lookup"><span data-stu-id="d9b59-105">Members</span></span>  
  
|<span data-ttu-id="d9b59-106">Member</span><span class="sxs-lookup"><span data-stu-id="d9b59-106">Member</span></span>|<span data-ttu-id="d9b59-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9b59-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="d9b59-108">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="d9b59-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="d9b59-109">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="d9b59-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="d9b59-110">Die Nummer des Builds.</span><span class="sxs-lookup"><span data-stu-id="d9b59-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="d9b59-111">Die untergeordnete Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="d9b59-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9b59-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9b59-112">Remarks</span></span>  
 <span data-ttu-id="d9b59-113">Ist die Versionsnummer 1.0.3705.288, 1 ist die Hauptversionsnummer, 0 ist die Nummer der Nebenversion, 3705 ist die Nummer des Builds und 288 ist das Sub-Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="d9b59-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9b59-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9b59-114">Requirements</span></span>  
 <span data-ttu-id="d9b59-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9b59-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9b59-116">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="d9b59-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d9b59-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9b59-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9b59-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9b59-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b59-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9b59-119">See also</span></span>

- [<span data-ttu-id="d9b59-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="d9b59-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d9b59-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d9b59-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
