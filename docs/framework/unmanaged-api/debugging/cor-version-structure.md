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
ms.openlocfilehash: ffbe571ebc3d14c12e57b1f805d77e56e97d12e1
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274173"
---
# <a name="cor_version-structure"></a><span data-ttu-id="15d75-102">COR_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="15d75-102">COR_VERSION Structure</span></span>
<span data-ttu-id="15d75-103">Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="15d75-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15d75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15d75-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="15d75-105">Member</span><span class="sxs-lookup"><span data-stu-id="15d75-105">Members</span></span>  
  
|<span data-ttu-id="15d75-106">Member</span><span class="sxs-lookup"><span data-stu-id="15d75-106">Member</span></span>|<span data-ttu-id="15d75-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15d75-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="15d75-108">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="15d75-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="15d75-109">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="15d75-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="15d75-110">Die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="15d75-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="15d75-111">Die teilbuildnummer.</span><span class="sxs-lookup"><span data-stu-id="15d75-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15d75-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15d75-112">Remarks</span></span>  
 <span data-ttu-id="15d75-113">Wenn die Versionsnummer 1.0.3705.288 ist, ist 1 die Hauptversionsnummer, 0 ist die neben Versionsnummer, 3705 ist die Buildnummer, und 288 ist die teilbuildnummer.</span><span class="sxs-lookup"><span data-stu-id="15d75-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15d75-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15d75-114">Requirements</span></span>  
 <span data-ttu-id="15d75-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15d75-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15d75-116">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="15d75-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="15d75-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15d75-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15d75-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15d75-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d75-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15d75-119">See also</span></span>

- [<span data-ttu-id="15d75-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="15d75-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="15d75-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="15d75-121">Debugging</span></span>](index.md)
