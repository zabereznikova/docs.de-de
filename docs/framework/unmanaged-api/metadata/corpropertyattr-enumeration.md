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
ms.openlocfilehash: b6651f30e0df3a5ffc29d310b9067e76761dcf01
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007532"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="78590-102">CorPropertyAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="78590-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="78590-103">Enthält Werte, in denen die Metadaten einer Eigenschaft beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="78590-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78590-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78590-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="78590-105">Member</span><span class="sxs-lookup"><span data-stu-id="78590-105">Members</span></span>  
  
|<span data-ttu-id="78590-106">Member</span><span class="sxs-lookup"><span data-stu-id="78590-106">Member</span></span>|<span data-ttu-id="78590-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78590-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="78590-108">Gibt an, dass die Eigenschaft speziell ist, und dass Ihr Name beschreibt, wie.</span><span class="sxs-lookup"><span data-stu-id="78590-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="78590-109">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="78590-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="78590-110">Gibt an, dass die Common Language Runtime Metadaten-internen APIs die Codierung des Eigenschafts namens überprüfen sollen.</span><span class="sxs-lookup"><span data-stu-id="78590-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="78590-111">Gibt an, dass die Eigenschaft einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="78590-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="78590-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="78590-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78590-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="78590-113">Requirements</span></span>  
 <span data-ttu-id="78590-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78590-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78590-115">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="78590-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="78590-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78590-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78590-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78590-117">See also</span></span>

- [<span data-ttu-id="78590-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="78590-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
