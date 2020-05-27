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
ms.openlocfilehash: 6da8a111f716906e403d85bc0b1a29eba7238100
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006063"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="117cd-102">CeeSectionAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="117cd-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="117cd-103">Stellt Werte bereit, die Attribute eines Abschnitts zur Verwendung durch die [ICeeGen](iceegen-interface.md) -Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="117cd-103">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="117cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="117cd-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="117cd-105">Member</span><span class="sxs-lookup"><span data-stu-id="117cd-105">Members</span></span>  
  
|<span data-ttu-id="117cd-106">Member</span><span class="sxs-lookup"><span data-stu-id="117cd-106">Member</span></span>|<span data-ttu-id="117cd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="117cd-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="117cd-108">Der Abschnitt weist keine Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="117cd-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="117cd-109">Der Abschnitt enthält initialisierte Daten, die nur gelesen, nicht aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="117cd-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="117cd-110">Der Abschnitt enthält initialisierte Daten, die gelesen oder aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="117cd-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="117cd-111">Der Abschnitt enthält ausführbaren Code, der gelesen und ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="117cd-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="117cd-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="117cd-112">Requirements</span></span>  
 <span data-ttu-id="117cd-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="117cd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="117cd-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="117cd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="117cd-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="117cd-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="117cd-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="117cd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117cd-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="117cd-117">See also</span></span>

- [<span data-ttu-id="117cd-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="117cd-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
