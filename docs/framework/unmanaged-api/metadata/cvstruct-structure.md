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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 195f311d58f2169d715bb33986ee6e591622f377
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445042"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="f30c2-102">CVStruct-Struktur</span><span class="sxs-lookup"><span data-stu-id="f30c2-102">CVStruct Structure</span></span>
<span data-ttu-id="f30c2-103">Enthält Informationen, die bei der Installation eines Moduls oder eines zusammengesetzten Abbilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f30c2-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f30c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f30c2-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="f30c2-105">Member</span><span class="sxs-lookup"><span data-stu-id="f30c2-105">Members</span></span>  
  
|<span data-ttu-id="f30c2-106">Member</span><span class="sxs-lookup"><span data-stu-id="f30c2-106">Member</span></span>|<span data-ttu-id="f30c2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f30c2-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f30c2-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="f30c2-108">Major</span></span>|<span data-ttu-id="f30c2-109">Nummer der Hauptversion-Builds.</span><span class="sxs-lookup"><span data-stu-id="f30c2-109">Major version build number.</span></span>|  
|<span data-ttu-id="f30c2-110">Gering</span><span class="sxs-lookup"><span data-stu-id="f30c2-110">Minor</span></span>|<span data-ttu-id="f30c2-111">Nummer der Nebenversion Build.</span><span class="sxs-lookup"><span data-stu-id="f30c2-111">Minor version build number.</span></span>|  
|<span data-ttu-id="f30c2-112">Sub</span><span class="sxs-lookup"><span data-stu-id="f30c2-112">Sub</span></span>|<span data-ttu-id="f30c2-113">Sub-Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="f30c2-113">Sub-build number.</span></span>|  
|<span data-ttu-id="f30c2-114">Build</span><span class="sxs-lookup"><span data-stu-id="f30c2-114">Build</span></span>|<span data-ttu-id="f30c2-115">Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="f30c2-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f30c2-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f30c2-116">Requirements</span></span>  
 <span data-ttu-id="f30c2-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f30c2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f30c2-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f30c2-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f30c2-119">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f30c2-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f30c2-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f30c2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30c2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f30c2-121">See Also</span></span>  
 [<span data-ttu-id="f30c2-122">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="f30c2-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
