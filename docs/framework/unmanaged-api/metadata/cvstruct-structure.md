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
ms.openlocfilehash: 4a5f06b3f79fed5dac5a6f07650e4fabd0aa5867
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142167"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="f65ad-102">CVStruct-Struktur</span><span class="sxs-lookup"><span data-stu-id="f65ad-102">CVStruct Structure</span></span>
<span data-ttu-id="f65ad-103">Enthält Informationen, die bei der Installation eines Moduls oder eines zusammengesetzten Abbilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f65ad-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f65ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f65ad-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="f65ad-105">Member</span><span class="sxs-lookup"><span data-stu-id="f65ad-105">Members</span></span>  
  
|<span data-ttu-id="f65ad-106">Member</span><span class="sxs-lookup"><span data-stu-id="f65ad-106">Member</span></span>|<span data-ttu-id="f65ad-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f65ad-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f65ad-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="f65ad-108">Major</span></span>|<span data-ttu-id="f65ad-109">Buildnummer der Hauptversion.</span><span class="sxs-lookup"><span data-stu-id="f65ad-109">Major version build number.</span></span>|  
|<span data-ttu-id="f65ad-110">Gering</span><span class="sxs-lookup"><span data-stu-id="f65ad-110">Minor</span></span>|<span data-ttu-id="f65ad-111">Nummer der Nebenversion erstellen.</span><span class="sxs-lookup"><span data-stu-id="f65ad-111">Minor version build number.</span></span>|  
|<span data-ttu-id="f65ad-112">Sub</span><span class="sxs-lookup"><span data-stu-id="f65ad-112">Sub</span></span>|<span data-ttu-id="f65ad-113">Sub-Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="f65ad-113">Sub-build number.</span></span>|  
|<span data-ttu-id="f65ad-114">Build</span><span class="sxs-lookup"><span data-stu-id="f65ad-114">Build</span></span>|<span data-ttu-id="f65ad-115">Build-Nummer.</span><span class="sxs-lookup"><span data-stu-id="f65ad-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f65ad-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f65ad-116">Requirements</span></span>  
 <span data-ttu-id="f65ad-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f65ad-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f65ad-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f65ad-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f65ad-119">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f65ad-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f65ad-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f65ad-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65ad-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f65ad-121">See also</span></span>

- [<span data-ttu-id="f65ad-122">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="f65ad-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
