---
title: CVStruct-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CVStruct
api_location: mscoree.dll
api_type: COM
f1_keywords: CVStruct
helpviewer_keywords: CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 95c1aeb0cacef929e99e5121f29e2f69b320caec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cvstruct-structure"></a><span data-ttu-id="e1e54-102">CVStruct-Struktur</span><span class="sxs-lookup"><span data-stu-id="e1e54-102">CVStruct Structure</span></span>
<span data-ttu-id="e1e54-103">Enthält Informationen, die bei der Installation eines Moduls oder eines zusammengesetzten Abbilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1e54-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1e54-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="e1e54-105">Member</span><span class="sxs-lookup"><span data-stu-id="e1e54-105">Members</span></span>  
  
|<span data-ttu-id="e1e54-106">Member</span><span class="sxs-lookup"><span data-stu-id="e1e54-106">Member</span></span>|<span data-ttu-id="e1e54-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1e54-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e1e54-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="e1e54-108">Major</span></span>|<span data-ttu-id="e1e54-109">Nummer der Hauptversion-Builds.</span><span class="sxs-lookup"><span data-stu-id="e1e54-109">Major version build number.</span></span>|  
|<span data-ttu-id="e1e54-110">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="e1e54-110">Minor</span></span>|<span data-ttu-id="e1e54-111">Nummer der Nebenversion Build.</span><span class="sxs-lookup"><span data-stu-id="e1e54-111">Minor version build number.</span></span>|  
|<span data-ttu-id="e1e54-112">Sub</span><span class="sxs-lookup"><span data-stu-id="e1e54-112">Sub</span></span>|<span data-ttu-id="e1e54-113">Sub-Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="e1e54-113">Sub-build number.</span></span>|  
|<span data-ttu-id="e1e54-114">Build</span><span class="sxs-lookup"><span data-stu-id="e1e54-114">Build</span></span>|<span data-ttu-id="e1e54-115">Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="e1e54-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1e54-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1e54-116">Requirements</span></span>  
 <span data-ttu-id="e1e54-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e54-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e54-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e1e54-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1e54-119">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e1e54-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1e54-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e54-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e54-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1e54-121">See Also</span></span>  
 [<span data-ttu-id="e1e54-122">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="e1e54-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
