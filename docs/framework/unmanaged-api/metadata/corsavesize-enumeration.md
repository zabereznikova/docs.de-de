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
ms.openlocfilehash: 81d47a3e4d72f991dc15924e7ff1ecc8df2e7322
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706053"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="fb211-102">CorSaveSize-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fb211-102">CorSaveSize Enumeration</span></span>

<span data-ttu-id="fb211-103">Enthält Werte, die den Genauigkeitsgrad angeben, der beim Abfragen der Größe eines Speichervorgangs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fb211-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb211-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb211-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="fb211-105">Member</span><span class="sxs-lookup"><span data-stu-id="fb211-105">Members</span></span>  
  
|<span data-ttu-id="fb211-106">Member</span><span class="sxs-lookup"><span data-stu-id="fb211-106">Member</span></span>|<span data-ttu-id="fb211-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb211-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="fb211-108">Gibt an, dass der Rückgabewert genau sein sollte.</span><span class="sxs-lookup"><span data-stu-id="fb211-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="fb211-109">Gibt an, dass der Rückgabewert geschätzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb211-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="fb211-110">Gibt an, dass verwerfbare Typen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb211-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb211-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fb211-111">Requirements</span></span>  

 <span data-ttu-id="fb211-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb211-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb211-113">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="fb211-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fb211-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb211-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb211-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb211-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb211-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb211-116">See also</span></span>

- [<span data-ttu-id="fb211-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="fb211-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
