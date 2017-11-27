---
title: CorCheckDuplicatesFor-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCheckDuplicatesFor
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCheckDuplicatesFor
helpviewer_keywords: CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d9bd0409f22e6ca47a7bc97bec634381158167da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="b2b66-102">CorCheckDuplicatesFor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b2b66-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="b2b66-103">Gibt die Metadatentoken, die auf Duplikate überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b2b66-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2b66-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="b2b66-105">Member</span><span class="sxs-lookup"><span data-stu-id="b2b66-105">Members</span></span>  
  
|<span data-ttu-id="b2b66-106">Member</span><span class="sxs-lookup"><span data-stu-id="b2b66-106">Member</span></span>|<span data-ttu-id="b2b66-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2b66-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="b2b66-108">Überprüfen Sie alle Metadatentoken für Duplikate an.</span><span class="sxs-lookup"><span data-stu-id="b2b66-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="b2b66-109">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2b66-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="b2b66-110">Überprüfen Sie die Metadatentoken für die Duplikate nicht.</span><span class="sxs-lookup"><span data-stu-id="b2b66-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="b2b66-111">Überprüfen Sie nach doppelten Einträgen `mdTypeDef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="b2b66-112">Überprüfen Sie nach doppelten Einträgen `mdInterfaceImpl` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="b2b66-113">Überprüfen Sie nach doppelten Einträgen `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="b2b66-114">Überprüfen Sie nach doppelten Einträgen `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="b2b66-115">Überprüfen Sie nach doppelten Einträgen `mdMemberRef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="b2b66-116">Überprüfen Sie nach doppelten Einträgen `mdCustomAttribute` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="b2b66-117">Überprüfen Sie nach doppelten Einträgen `mdParamDef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="b2b66-118">Überprüfen Sie nach doppelten Einträgen `mdPermission` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="b2b66-119">Überprüfen Sie nach doppelten Einträgen `mdProperty` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="b2b66-120">Überprüfen Sie nach doppelten Einträgen `mdEvent` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="b2b66-121">Überprüfen Sie nach doppelten Einträgen `mdFieldDef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="b2b66-122">Überprüfen Sie nach doppelten Einträgen `mdSignature` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="b2b66-123">Überprüfen Sie nach doppelten Einträgen `mdModuleRef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="b2b66-124">Überprüfen Sie nach doppelten Einträgen `mdTypeSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="b2b66-125">Überprüfen Sie nach doppelten Einträgen `mdImplMap` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="b2b66-126">Überprüfen Sie nach doppelten Einträgen `mdAssemblyRef` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="b2b66-127">Überprüfen Sie nach doppelten Einträgen `mdFile` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="b2b66-128">Überprüfen Sie nach doppelten Einträgen `mdExportedType` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="b2b66-129">Überprüfen Sie nach doppelten Einträgen `mdManifestResource` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="b2b66-130">Überprüfen Sie nach doppelten Einträgen `mdGenericParam` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="b2b66-131">Überprüfen Sie nach doppelten Einträgen `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="b2b66-132">Überprüfen Sie nach doppelten Einträgen `mdGenericParamConstraint` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="b2b66-133">Überprüfen Sie nach doppelten Einträgen `mdAssembly` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="b2b66-134">Überprüfen Sie nach doppelten Einträgen `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, und `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="b2b66-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2b66-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2b66-135">Requirements</span></span>  
 <span data-ttu-id="b2b66-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2b66-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2b66-137">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b2b66-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b2b66-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2b66-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b66-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2b66-139">See Also</span></span>  
 [<span data-ttu-id="b2b66-140">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="b2b66-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
