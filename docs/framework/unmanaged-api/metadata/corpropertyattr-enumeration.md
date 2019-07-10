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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fb70d530af24798636972de0a4d6280dbcb8f1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781629"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="01a37-102">CorPropertyAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="01a37-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="01a37-103">Enthält Werte, in denen die Metadaten einer Eigenschaft beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="01a37-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01a37-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="01a37-105">Member</span><span class="sxs-lookup"><span data-stu-id="01a37-105">Members</span></span>  
  
|<span data-ttu-id="01a37-106">Member</span><span class="sxs-lookup"><span data-stu-id="01a37-106">Member</span></span>|<span data-ttu-id="01a37-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01a37-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="01a37-108">Gibt an, dass die Eigenschaft spezielle und seinen Namen wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="01a37-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="01a37-109">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="01a37-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="01a37-110">Gibt an, dass die common Language Runtime-Metadaten über interne APIs überprüfen soll, die die Codierung der Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="01a37-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="01a37-111">Gibt an, dass die Eigenschaft einen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="01a37-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="01a37-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="01a37-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01a37-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01a37-113">Requirements</span></span>  
 <span data-ttu-id="01a37-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01a37-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01a37-115">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="01a37-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="01a37-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01a37-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a37-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01a37-117">See also</span></span>

- [<span data-ttu-id="01a37-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="01a37-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
