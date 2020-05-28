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
ms.openlocfilehash: 84791eba7c95d3278bd4650bd7d660e98fcb79d8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008916"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="b7bbc-102">CVStruct-Struktur</span><span class="sxs-lookup"><span data-stu-id="b7bbc-102">CVStruct Structure</span></span>
<span data-ttu-id="b7bbc-103">Enthält Informationen, die bei der Installation eines Moduls oder eines zusammengesetzten Abbilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7bbc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7bbc-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="b7bbc-105">Member</span><span class="sxs-lookup"><span data-stu-id="b7bbc-105">Members</span></span>  
  
|<span data-ttu-id="b7bbc-106">Member</span><span class="sxs-lookup"><span data-stu-id="b7bbc-106">Member</span></span>|<span data-ttu-id="b7bbc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7bbc-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b7bbc-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="b7bbc-108">Major</span></span>|<span data-ttu-id="b7bbc-109">Buildnummer der Hauptversion.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-109">Major version build number.</span></span>|  
|<span data-ttu-id="b7bbc-110">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="b7bbc-110">Minor</span></span>|<span data-ttu-id="b7bbc-111">Buildnummer der neben Version.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-111">Minor version build number.</span></span>|  
|<span data-ttu-id="b7bbc-112">Sub</span><span class="sxs-lookup"><span data-stu-id="b7bbc-112">Sub</span></span>|<span data-ttu-id="b7bbc-113">Subbuildnummer.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-113">Sub-build number.</span></span>|  
|<span data-ttu-id="b7bbc-114">Entwickeln</span><span class="sxs-lookup"><span data-stu-id="b7bbc-114">Build</span></span>|<span data-ttu-id="b7bbc-115">Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7bbc-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b7bbc-116">Requirements</span></span>  
 <span data-ttu-id="b7bbc-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7bbc-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7bbc-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b7bbc-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7bbc-119">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7bbc-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7bbc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bbc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7bbc-121">See also</span></span>

- [<span data-ttu-id="b7bbc-122">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="b7bbc-122">Metadata Structures</span></span>](metadata-structures.md)
