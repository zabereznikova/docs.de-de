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
ms.openlocfilehash: f1a0fff266e964b506b2dc7c4030caa54abaa5ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171820"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="f8013-102">CorPropertyAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f8013-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="f8013-103">Enthält Werte, in denen die Metadaten einer Eigenschaft beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f8013-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8013-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8013-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="f8013-105">Member</span><span class="sxs-lookup"><span data-stu-id="f8013-105">Members</span></span>  
  
|<span data-ttu-id="f8013-106">Member</span><span class="sxs-lookup"><span data-stu-id="f8013-106">Member</span></span>|<span data-ttu-id="f8013-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8013-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="f8013-108">Gibt an, dass die Eigenschaft spezielle und seinen Namen wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="f8013-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="f8013-109">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="f8013-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="f8013-110">Gibt an, dass die common Language Runtime-Metadaten über interne APIs überprüfen soll, die die Codierung der Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f8013-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="f8013-111">Gibt an, dass die Eigenschaft einen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="f8013-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="f8013-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8013-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8013-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8013-113">Requirements</span></span>  
 <span data-ttu-id="f8013-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8013-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8013-115">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f8013-115">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="f8013-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f8013-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8013-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8013-117">See also</span></span>

- [<span data-ttu-id="f8013-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="f8013-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
