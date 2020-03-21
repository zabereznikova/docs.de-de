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
ms.openlocfilehash: 13a4364244f7d0076d77d14c3e3ef161e3872bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176135"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="40c2e-102">CorSaveSize-Enumeration</span><span class="sxs-lookup"><span data-stu-id="40c2e-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="40c2e-103">Enthält Werte, die den Genauigkeitsgrad angeben, der beim Abfragen der Größe eines Speichervorgangs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="40c2e-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c2e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40c2e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="40c2e-105">Members</span><span class="sxs-lookup"><span data-stu-id="40c2e-105">Members</span></span>  
  
|<span data-ttu-id="40c2e-106">Member</span><span class="sxs-lookup"><span data-stu-id="40c2e-106">Member</span></span>|<span data-ttu-id="40c2e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40c2e-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="40c2e-108">Gibt an, dass der Rückgabewert genau sein soll.</span><span class="sxs-lookup"><span data-stu-id="40c2e-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="40c2e-109">Gibt an, dass der Rückgabewert geschätzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="40c2e-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="40c2e-110">Gibt an, dass verwerfliche Typen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="40c2e-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40c2e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="40c2e-111">Requirements</span></span>  
 <span data-ttu-id="40c2e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40c2e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40c2e-113">**Kopfzeile:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="40c2e-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="40c2e-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="40c2e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40c2e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40c2e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c2e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40c2e-116">See also</span></span>

- [<span data-ttu-id="40c2e-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="40c2e-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
