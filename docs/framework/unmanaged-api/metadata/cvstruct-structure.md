---
title: CVStruct-Struktur
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: 19ee3097dfe80ba9dcbdaf316db0fd165b50abc6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436430"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="b5c97-102">CVStruct-Struktur</span><span class="sxs-lookup"><span data-stu-id="b5c97-102">CVStruct Structure</span></span>
<span data-ttu-id="b5c97-103">Enthält Informationen, die bei der Installation eines Moduls oder eines zusammengesetzten Abbilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5c97-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5c97-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="b5c97-105">Member</span><span class="sxs-lookup"><span data-stu-id="b5c97-105">Members</span></span>  
  
|<span data-ttu-id="b5c97-106">Member</span><span class="sxs-lookup"><span data-stu-id="b5c97-106">Member</span></span>|<span data-ttu-id="b5c97-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5c97-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b5c97-108">Major</span><span class="sxs-lookup"><span data-stu-id="b5c97-108">Major</span></span>|<span data-ttu-id="b5c97-109">Major version build number.</span><span class="sxs-lookup"><span data-stu-id="b5c97-109">Major version build number.</span></span>|  
|<span data-ttu-id="b5c97-110">Minor</span><span class="sxs-lookup"><span data-stu-id="b5c97-110">Minor</span></span>|<span data-ttu-id="b5c97-111">Minor version build number.</span><span class="sxs-lookup"><span data-stu-id="b5c97-111">Minor version build number.</span></span>|  
|<span data-ttu-id="b5c97-112">Sub</span><span class="sxs-lookup"><span data-stu-id="b5c97-112">Sub</span></span>|<span data-ttu-id="b5c97-113">Sub-build number.</span><span class="sxs-lookup"><span data-stu-id="b5c97-113">Sub-build number.</span></span>|  
|<span data-ttu-id="b5c97-114">Build</span><span class="sxs-lookup"><span data-stu-id="b5c97-114">Build</span></span>|<span data-ttu-id="b5c97-115">Build number.</span><span class="sxs-lookup"><span data-stu-id="b5c97-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5c97-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5c97-116">Requirements</span></span>  
 <span data-ttu-id="b5c97-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5c97-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5c97-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5c97-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5c97-119">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5c97-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5c97-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5c97-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c97-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5c97-121">See also</span></span>

- [<span data-ttu-id="b5c97-122">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="b5c97-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
