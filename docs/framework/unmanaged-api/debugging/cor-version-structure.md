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
ms.openlocfilehash: 874c0520482cc5a3bbfcdd17924edee84fe91ff5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675320"
---
# <a name="cor_version-structure"></a><span data-ttu-id="6720f-102">COR_VERSION-Struktur</span><span class="sxs-lookup"><span data-stu-id="6720f-102">COR_VERSION Structure</span></span>

<span data-ttu-id="6720f-103">Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6720f-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6720f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6720f-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="6720f-105">Member</span><span class="sxs-lookup"><span data-stu-id="6720f-105">Members</span></span>  
  
|<span data-ttu-id="6720f-106">Member</span><span class="sxs-lookup"><span data-stu-id="6720f-106">Member</span></span>|<span data-ttu-id="6720f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6720f-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="6720f-108">Die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="6720f-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="6720f-109">Die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="6720f-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="6720f-110">Die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="6720f-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="6720f-111">Die teilbuildnummer.</span><span class="sxs-lookup"><span data-stu-id="6720f-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6720f-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6720f-112">Remarks</span></span>  

 <span data-ttu-id="6720f-113">Wenn die Versionsnummer 1.0.3705.288 ist, ist 1 die Hauptversionsnummer, 0 ist die neben Versionsnummer, 3705 ist die Buildnummer, und 288 ist die teilbuildnummer.</span><span class="sxs-lookup"><span data-stu-id="6720f-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6720f-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6720f-114">Requirements</span></span>  

 <span data-ttu-id="6720f-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6720f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6720f-116">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="6720f-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="6720f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6720f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6720f-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6720f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6720f-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6720f-119">See also</span></span>

- [<span data-ttu-id="6720f-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="6720f-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="6720f-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6720f-121">Debugging</span></span>](index.md)
