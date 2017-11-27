---
title: CeeSectionAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionAttr
helpviewer_keywords: CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f0c87c0e5703f13cf843ca5a4213440af71bd12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="15afd-102">CeeSectionAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="15afd-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="15afd-103">Enthält Werte, die Attribute eines Abschnitts zur Verwendung durch Angeben der [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="15afd-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15afd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15afd-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="15afd-105">Member</span><span class="sxs-lookup"><span data-stu-id="15afd-105">Members</span></span>  
  
|<span data-ttu-id="15afd-106">Member</span><span class="sxs-lookup"><span data-stu-id="15afd-106">Member</span></span>|<span data-ttu-id="15afd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15afd-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="15afd-108">Abschnitt weist keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="15afd-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="15afd-109">Abschnitt enthält initialisierte Daten, die nur können nicht aktualisiert gelesen werden werden.</span><span class="sxs-lookup"><span data-stu-id="15afd-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="15afd-110">Abschnitt enthält initialisierte Daten, die gelesen oder aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="15afd-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="15afd-111">Abschnitt enthält ausführbaren Code, der gelesen und ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="15afd-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15afd-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15afd-112">Requirements</span></span>  
 <span data-ttu-id="15afd-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15afd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15afd-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15afd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15afd-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15afd-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15afd-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15afd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15afd-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15afd-117">See Also</span></span>  
 [<span data-ttu-id="15afd-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="15afd-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
