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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d56be8c6f224010da22803894524299c0d376ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443536"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="861bf-102">CorGenericParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="861bf-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="861bf-103">Enthält Werte, die beschreiben, die <xref:System.Type> Parameter für generische Typen, wie in Aufrufen verwendet [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="861bf-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="861bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="861bf-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="861bf-105">Member</span><span class="sxs-lookup"><span data-stu-id="861bf-105">Members</span></span>  
  
|<span data-ttu-id="861bf-106">Member</span><span class="sxs-lookup"><span data-stu-id="861bf-106">Member</span></span>|<span data-ttu-id="861bf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="861bf-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="861bf-108">Parametervarianz gilt nur für generische Parameter für Schnittstellen und Delegaten.</span><span class="sxs-lookup"><span data-stu-id="861bf-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="861bf-109">Gibt das Fehlen der Varianz.</span><span class="sxs-lookup"><span data-stu-id="861bf-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="861bf-110">Gibt die Kovarianz an.</span><span class="sxs-lookup"><span data-stu-id="861bf-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="861bf-111">Gibt Kontravarianz an.</span><span class="sxs-lookup"><span data-stu-id="861bf-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="861bf-112">Besondere Einschränkungen gelten können, für jede <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="861bf-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="861bf-113">Gibt an, dass keine Einschränkung gilt die <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="861bf-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="861bf-114">Gibt an, dass die <xref:System.Type> Parameter muss ein Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="861bf-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="861bf-115">Gibt an, dass die <xref:System.Type> -Parameter muss ein Werttyp, der einen null-Wert nicht mehr möglich sein.</span><span class="sxs-lookup"><span data-stu-id="861bf-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="861bf-116">Gibt an, dass die <xref:System.Type> Parameter muss einen öffentlichen Standardkonstruktor, der keine Parameter akzeptiert haben.</span><span class="sxs-lookup"><span data-stu-id="861bf-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="861bf-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="861bf-117">Requirements</span></span>  
 <span data-ttu-id="861bf-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="861bf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="861bf-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="861bf-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="861bf-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="861bf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="861bf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="861bf-121">See Also</span></span>  
 [<span data-ttu-id="861bf-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="861bf-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
