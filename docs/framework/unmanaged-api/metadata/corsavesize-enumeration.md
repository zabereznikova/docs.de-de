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
ms.openlocfilehash: c1e7bbac17d9a9ae191a5ad6d69b52a806383562
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781600"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="4aec4-102">CorSaveSize-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4aec4-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="4aec4-103">Enthält Werte, die den Genauigkeitsgrad angeben, der beim Abfragen der Größe eines Speichervorgangs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4aec4-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aec4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4aec4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="4aec4-105">Member</span><span class="sxs-lookup"><span data-stu-id="4aec4-105">Members</span></span>  
  
|<span data-ttu-id="4aec4-106">Member</span><span class="sxs-lookup"><span data-stu-id="4aec4-106">Member</span></span>|<span data-ttu-id="4aec4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aec4-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="4aec4-108">Gibt an, dass der zurückgegebene Wert genau sein soll.</span><span class="sxs-lookup"><span data-stu-id="4aec4-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="4aec4-109">Gibt an, dass der Rückgabewert geschätzt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="4aec4-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="4aec4-110">Gibt an, dass es sich bei entfernbare Typ entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4aec4-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4aec4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4aec4-111">Requirements</span></span>  
 <span data-ttu-id="4aec4-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aec4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aec4-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4aec4-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4aec4-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4aec4-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4aec4-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aec4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aec4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4aec4-116">See also</span></span>

- [<span data-ttu-id="4aec4-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="4aec4-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
