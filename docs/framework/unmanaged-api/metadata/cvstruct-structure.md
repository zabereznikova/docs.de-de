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
ms.openlocfilehash: db36b94fafe20b58b9bcbb886b8d285326960f67
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715575"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="68eeb-102">CVStruct-Struktur</span><span class="sxs-lookup"><span data-stu-id="68eeb-102">CVStruct Structure</span></span>

<span data-ttu-id="68eeb-103">Enthält Informationen, die bei der Installation eines Moduls oder eines zusammengesetzten Abbilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68eeb-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68eeb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68eeb-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="68eeb-105">Member</span><span class="sxs-lookup"><span data-stu-id="68eeb-105">Members</span></span>  
  
|<span data-ttu-id="68eeb-106">Member</span><span class="sxs-lookup"><span data-stu-id="68eeb-106">Member</span></span>|<span data-ttu-id="68eeb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="68eeb-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="68eeb-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="68eeb-108">Major</span></span>|<span data-ttu-id="68eeb-109">Buildnummer der Hauptversion.</span><span class="sxs-lookup"><span data-stu-id="68eeb-109">Major version build number.</span></span>|  
|<span data-ttu-id="68eeb-110">Gering</span><span class="sxs-lookup"><span data-stu-id="68eeb-110">Minor</span></span>|<span data-ttu-id="68eeb-111">Buildnummer der neben Version.</span><span class="sxs-lookup"><span data-stu-id="68eeb-111">Minor version build number.</span></span>|  
|<span data-ttu-id="68eeb-112">Sub</span><span class="sxs-lookup"><span data-stu-id="68eeb-112">Sub</span></span>|<span data-ttu-id="68eeb-113">Subbuildnummer.</span><span class="sxs-lookup"><span data-stu-id="68eeb-113">Sub-build number.</span></span>|  
|<span data-ttu-id="68eeb-114">Erstellen</span><span class="sxs-lookup"><span data-stu-id="68eeb-114">Build</span></span>|<span data-ttu-id="68eeb-115">Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="68eeb-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68eeb-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="68eeb-116">Requirements</span></span>  

 <span data-ttu-id="68eeb-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68eeb-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68eeb-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="68eeb-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68eeb-119">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="68eeb-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68eeb-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68eeb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68eeb-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68eeb-121">See also</span></span>

- [<span data-ttu-id="68eeb-122">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="68eeb-122">Metadata Structures</span></span>](metadata-structures.md)
