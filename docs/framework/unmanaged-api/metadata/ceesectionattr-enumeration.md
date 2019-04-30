---
title: CeeSectionAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c317524cefd7ed654e76bdd7051cdcd7653062db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905894"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="d2034-102">CeeSectionAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2034-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="d2034-103">Enthält Werte, die Attribute eines Abschnitts für die Verwendung durch Angeben der [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d2034-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2034-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2034-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d2034-105">Member</span><span class="sxs-lookup"><span data-stu-id="d2034-105">Members</span></span>  
  
|<span data-ttu-id="d2034-106">Member</span><span class="sxs-lookup"><span data-stu-id="d2034-106">Member</span></span>|<span data-ttu-id="d2034-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2034-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="d2034-108">Abschnitt besitzt keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="d2034-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="d2034-109">Abschnitt initialisierte Daten enthält, die nur können nicht aktualisiert gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="d2034-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="d2034-110">Abschnitt initialisierte Daten enthält, die gelesen oder aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="d2034-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="d2034-111">Abschnitt enthält die ausführbaren Code, der gelesen und ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="d2034-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2034-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2034-112">Requirements</span></span>  
 <span data-ttu-id="d2034-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2034-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2034-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2034-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2034-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d2034-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2034-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2034-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2034-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2034-117">See also</span></span>

- [<span data-ttu-id="d2034-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d2034-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
