---
title: CorGenericParamAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e40613d790baed5bd89bee1e1f5ca57043bfe76a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="91f41-102">CorGenericParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="91f41-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="91f41-103">Enthält Werte, die beschreiben, die <xref:System.Type> Parameter für generische Typen, wie in Aufrufen verwendet [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="91f41-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f41-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91f41-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="91f41-105">Member</span><span class="sxs-lookup"><span data-stu-id="91f41-105">Members</span></span>  
  
|<span data-ttu-id="91f41-106">Member</span><span class="sxs-lookup"><span data-stu-id="91f41-106">Member</span></span>|<span data-ttu-id="91f41-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91f41-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="91f41-108">Parametervarianz gilt nur für generische Parameter für Schnittstellen und Delegaten.</span><span class="sxs-lookup"><span data-stu-id="91f41-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="91f41-109">Gibt das Fehlen der Varianz.</span><span class="sxs-lookup"><span data-stu-id="91f41-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="91f41-110">Gibt die Kovarianz an.</span><span class="sxs-lookup"><span data-stu-id="91f41-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="91f41-111">Gibt Kontravarianz an.</span><span class="sxs-lookup"><span data-stu-id="91f41-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="91f41-112">Besondere Einschränkungen gelten können, für jede <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="91f41-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="91f41-113">Gibt an, dass keine Einschränkung gilt die <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="91f41-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="91f41-114">Gibt an, dass die <xref:System.Type> Parameter muss ein Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="91f41-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="91f41-115">Gibt an, dass die <xref:System.Type> -Parameter muss ein Werttyp, der einen null-Wert nicht mehr möglich sein.</span><span class="sxs-lookup"><span data-stu-id="91f41-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="91f41-116">Gibt an, dass die <xref:System.Type> Parameter muss einen öffentlichen Standardkonstruktor, der keine Parameter akzeptiert haben.</span><span class="sxs-lookup"><span data-stu-id="91f41-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91f41-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91f41-117">Requirements</span></span>  
 <span data-ttu-id="91f41-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91f41-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f41-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="91f41-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="91f41-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f41-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f41-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91f41-121">See Also</span></span>  
 [<span data-ttu-id="91f41-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="91f41-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
