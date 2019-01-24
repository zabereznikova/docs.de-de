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
ms.openlocfilehash: 5e88dd0053ec7562d6223c18479f4a4fadc68c12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701793"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="d7cab-102">CeeSectionAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d7cab-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="d7cab-103">Enthält Werte, die Attribute eines Abschnitts für die Verwendung durch Angeben der [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d7cab-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7cab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7cab-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d7cab-105">Member</span><span class="sxs-lookup"><span data-stu-id="d7cab-105">Members</span></span>  
  
|<span data-ttu-id="d7cab-106">Member</span><span class="sxs-lookup"><span data-stu-id="d7cab-106">Member</span></span>|<span data-ttu-id="d7cab-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7cab-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="d7cab-108">Abschnitt besitzt keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="d7cab-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="d7cab-109">Abschnitt initialisierte Daten enthält, die nur können nicht aktualisiert gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="d7cab-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="d7cab-110">Abschnitt initialisierte Daten enthält, die gelesen oder aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="d7cab-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="d7cab-111">Abschnitt enthält die ausführbaren Code, der gelesen und ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="d7cab-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7cab-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7cab-112">Requirements</span></span>  
 <span data-ttu-id="d7cab-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7cab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7cab-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7cab-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7cab-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d7cab-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7cab-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7cab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7cab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7cab-117">See also</span></span>
- [<span data-ttu-id="d7cab-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d7cab-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
