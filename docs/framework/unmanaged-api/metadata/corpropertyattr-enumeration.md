---
title: CorPropertyAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: 2d49a146a465210cea8466a75666ca3f800b090b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450144"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="2ccb2-102">CorPropertyAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2ccb2-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="2ccb2-103">Enthält Werte, in denen die Metadaten einer Eigenschaft beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="2ccb2-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ccb2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ccb2-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="2ccb2-105">Member</span><span class="sxs-lookup"><span data-stu-id="2ccb2-105">Members</span></span>  
  
|<span data-ttu-id="2ccb2-106">Member</span><span class="sxs-lookup"><span data-stu-id="2ccb2-106">Member</span></span>|<span data-ttu-id="2ccb2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ccb2-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="2ccb2-108">Specifies that the property is special, and that its name describes how.</span><span class="sxs-lookup"><span data-stu-id="2ccb2-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="2ccb2-109">Reserved for internal use by the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="2ccb2-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="2ccb2-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span><span class="sxs-lookup"><span data-stu-id="2ccb2-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="2ccb2-111">Specifies that the property has a default value.</span><span class="sxs-lookup"><span data-stu-id="2ccb2-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="2ccb2-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ccb2-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ccb2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ccb2-113">Requirements</span></span>  
 <span data-ttu-id="2ccb2-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ccb2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ccb2-115">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2ccb2-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2ccb2-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ccb2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ccb2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ccb2-117">See also</span></span>

- [<span data-ttu-id="2ccb2-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="2ccb2-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
