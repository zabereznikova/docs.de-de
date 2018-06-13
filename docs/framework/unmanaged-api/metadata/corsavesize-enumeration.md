---
title: CorSaveSize-Enumeration
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f9f95b0cf19acb677daf7f7401d21cc81864a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447606"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="531f7-102">CorSaveSize-Enumeration</span><span class="sxs-lookup"><span data-stu-id="531f7-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="531f7-103">Enthält Werte, die den Genauigkeitsgrad angeben, der beim Abfragen der Größe eines Speichervorgangs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="531f7-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="531f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="531f7-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="531f7-105">Member</span><span class="sxs-lookup"><span data-stu-id="531f7-105">Members</span></span>  
  
|<span data-ttu-id="531f7-106">Member</span><span class="sxs-lookup"><span data-stu-id="531f7-106">Member</span></span>|<span data-ttu-id="531f7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="531f7-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="531f7-108">Gibt an, dass der Rückgabewert exakt sein muss.</span><span class="sxs-lookup"><span data-stu-id="531f7-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="531f7-109">Gibt an, dass der Rückgabewert geschätzt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="531f7-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="531f7-110">Gibt an, dass es sich bei entfernbare Typen entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="531f7-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="531f7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="531f7-111">Requirements</span></span>  
 <span data-ttu-id="531f7-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="531f7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="531f7-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="531f7-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="531f7-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="531f7-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="531f7-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="531f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531f7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="531f7-116">See Also</span></span>  
 [<span data-ttu-id="531f7-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="531f7-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
