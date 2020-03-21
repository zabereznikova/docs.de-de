---
title: CorCheckDuplicatesFor-Enumeration
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176187"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="90722-102">CorCheckDuplicatesFor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="90722-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="90722-103">Gibt die Metadatentoken an, die auf Duplikate überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="90722-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90722-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90722-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="90722-105">Members</span><span class="sxs-lookup"><span data-stu-id="90722-105">Members</span></span>  
  
|<span data-ttu-id="90722-106">Member</span><span class="sxs-lookup"><span data-stu-id="90722-106">Member</span></span>|<span data-ttu-id="90722-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90722-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="90722-108">Überprüfen Sie alle Metadatentoken auf Duplikate.</span><span class="sxs-lookup"><span data-stu-id="90722-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="90722-109">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="90722-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="90722-110">Überprüfen Sie Metadatentoken nicht auf Duplikate.</span><span class="sxs-lookup"><span data-stu-id="90722-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="90722-111">Überprüfen Sie, `mdTypeDef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="90722-112">Überprüfen Sie, `mdInterfaceImpl` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="90722-113">Überprüfen Sie, `mdMethodDef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="90722-114">Überprüfen Sie, `mdTypeRef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="90722-115">Überprüfen Sie, `mdMemberRef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="90722-116">Überprüfen Sie, `mdCustomAttribute` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="90722-117">Überprüfen Sie, `mdParamDef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="90722-118">Überprüfen Sie, `mdPermission` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="90722-119">Überprüfen Sie, `mdProperty` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="90722-120">Überprüfen Sie, `mdEvent` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="90722-121">Überprüfen Sie, `mdFieldDef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="90722-122">Überprüfen Sie, `mdSignature` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="90722-123">Überprüfen Sie, `mdModuleRef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="90722-124">Überprüfen Sie, `mdTypeSpec` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="90722-125">Überprüfen Sie, `mdImplMap` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="90722-126">Überprüfen Sie, `mdAssemblyRef` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="90722-127">Überprüfen Sie, `mdFile` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="90722-128">Überprüfen Sie, `mdExportedType` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="90722-129">Überprüfen Sie, `mdManifestResource` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="90722-130">Überprüfen Sie, `mdGenericParam` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="90722-131">Überprüfen Sie, `mdMethodSpec` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="90722-132">Überprüfen Sie, `mdGenericParamConstraint` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="90722-133">Überprüfen Sie, `mdAssembly` ob Duplikate von Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="90722-134">Überprüfen Sie, `mdMemberRef`ob `mdTypeRef` `mdSignature`Duplikate von , , , `mdTypeSpec`und `mdMethodSpec` Token vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90722-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90722-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="90722-135">Requirements</span></span>  
 <span data-ttu-id="90722-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90722-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90722-137">**Kopfzeile:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="90722-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="90722-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90722-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90722-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90722-139">See also</span></span>

- [<span data-ttu-id="90722-140">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="90722-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
