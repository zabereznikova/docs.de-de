---
title: CorGenericParamAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176174"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="fe65a-102">CorGenericParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fe65a-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="fe65a-103">Enthält Werte, <xref:System.Type> die die Parameter für generische Typen beschreiben, wie sie in Aufrufen von [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe65a-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe65a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe65a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="fe65a-105">Members</span><span class="sxs-lookup"><span data-stu-id="fe65a-105">Members</span></span>  
  
|<span data-ttu-id="fe65a-106">Member</span><span class="sxs-lookup"><span data-stu-id="fe65a-106">Member</span></span>|<span data-ttu-id="fe65a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe65a-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="fe65a-108">Die Parameterabweichung gilt nur für generische Parameter für Schnittstellen und Delegaten.</span><span class="sxs-lookup"><span data-stu-id="fe65a-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="fe65a-109">Gibt das Fehlen von Abweichungen an.</span><span class="sxs-lookup"><span data-stu-id="fe65a-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="fe65a-110">Gibt kovariantanzan.</span><span class="sxs-lookup"><span data-stu-id="fe65a-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="fe65a-111">Zeigt die Kontravarianz an.</span><span class="sxs-lookup"><span data-stu-id="fe65a-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="fe65a-112">Für jeden Parameter können <xref:System.Type> spezielle Einschränkungen gelten.</span><span class="sxs-lookup"><span data-stu-id="fe65a-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="fe65a-113">Gibt an, dass <xref:System.Type> keine Einschränkung auf den Parameter angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe65a-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="fe65a-114">Gibt an, dass der <xref:System.Type> Parameter ein Referenztyp sein muss.</span><span class="sxs-lookup"><span data-stu-id="fe65a-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="fe65a-115">Gibt an, dass der <xref:System.Type> Parameter ein Werttyp sein muss, der kein NULL-Wert sein kann.</span><span class="sxs-lookup"><span data-stu-id="fe65a-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="fe65a-116">Gibt an, dass der <xref:System.Type> Parameter über einen öffentlichen Standardkonstruktor verfügen muss, der keine Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="fe65a-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe65a-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fe65a-117">Requirements</span></span>  
 <span data-ttu-id="fe65a-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe65a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe65a-119">**Kopfzeile:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="fe65a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fe65a-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe65a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe65a-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe65a-121">See also</span></span>

- [<span data-ttu-id="fe65a-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="fe65a-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
