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
ms.openlocfilehash: ea50430c3ae6cef9b47880bcb8ad969f62ce9c39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704915"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="bda3a-102">CorGenericParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bda3a-102">CorGenericParamAttr Enumeration</span></span>

<span data-ttu-id="bda3a-103">Enthält Werte, die die <xref:System.Type> Parameter für generische Typen beschreiben, wie Sie in Aufrufen von [IMetaDataEmit2::D efinegenericparam](imetadataemit2-definegenericparam-method.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bda3a-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bda3a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="bda3a-105">Member</span><span class="sxs-lookup"><span data-stu-id="bda3a-105">Members</span></span>  
  
|<span data-ttu-id="bda3a-106">Member</span><span class="sxs-lookup"><span data-stu-id="bda3a-106">Member</span></span>|<span data-ttu-id="bda3a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bda3a-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="bda3a-108">Die Parameter Varianz gilt nur für generische Parameter für Schnittstellen und Delegaten.</span><span class="sxs-lookup"><span data-stu-id="bda3a-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="bda3a-109">Gibt an, dass keine Varianz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bda3a-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="bda3a-110">Gibt Kovarianz an.</span><span class="sxs-lookup"><span data-stu-id="bda3a-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="bda3a-111">Gibt kontra Varianz an.</span><span class="sxs-lookup"><span data-stu-id="bda3a-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="bda3a-112">Besondere Einschränkungen können auf jeden Parameter angewendet werden <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="bda3a-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="bda3a-113">Gibt an, dass keine Einschränkung auf den-Parameter angewendet wird <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="bda3a-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="bda3a-114">Gibt an, dass der <xref:System.Type> Parameter ein Verweistyp sein muss.</span><span class="sxs-lookup"><span data-stu-id="bda3a-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="bda3a-115">Gibt an, dass der <xref:System.Type> Parameter ein Werttyp sein muss, der kein NULL-Wert sein darf.</span><span class="sxs-lookup"><span data-stu-id="bda3a-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="bda3a-116">Gibt an, dass der <xref:System.Type> Parameter über einen öffentlichen Standardkonstruktor verfügen muss, der keine Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="bda3a-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bda3a-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bda3a-117">Requirements</span></span>  

 <span data-ttu-id="bda3a-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda3a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda3a-119">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="bda3a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bda3a-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda3a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda3a-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bda3a-121">See also</span></span>

- [<span data-ttu-id="bda3a-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="bda3a-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
