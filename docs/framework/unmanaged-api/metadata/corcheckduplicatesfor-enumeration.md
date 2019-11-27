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
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443786"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="ad61e-102">CorCheckDuplicatesFor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ad61e-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="ad61e-103">Gibt die Metadatentoken an, die auf Duplikate geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="ad61e-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad61e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad61e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ad61e-105">Member</span><span class="sxs-lookup"><span data-stu-id="ad61e-105">Members</span></span>  
  
|<span data-ttu-id="ad61e-106">Member</span><span class="sxs-lookup"><span data-stu-id="ad61e-106">Member</span></span>|<span data-ttu-id="ad61e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad61e-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="ad61e-108">Überprüfen Sie alle Metadatentoken auf Duplikate.</span><span class="sxs-lookup"><span data-stu-id="ad61e-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="ad61e-109">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad61e-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="ad61e-110">Überprüfen Sie die Metadatentoken nicht auf Duplikate.</span><span class="sxs-lookup"><span data-stu-id="ad61e-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="ad61e-111">Überprüfen Sie, ob `mdTypeDef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="ad61e-112">Überprüfen Sie, ob `mdInterfaceImpl` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="ad61e-113">Überprüfen Sie, ob `mdMethodDef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="ad61e-114">Überprüfen Sie, ob `mdTypeRef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="ad61e-115">Überprüfen Sie, ob `mdMemberRef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="ad61e-116">Überprüfen Sie, ob `mdCustomAttribute` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="ad61e-117">Überprüfen Sie, ob `mdParamDef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="ad61e-118">Überprüfen Sie, ob `mdPermission` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="ad61e-119">Überprüfen Sie, ob `mdProperty` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="ad61e-120">Überprüfen Sie, ob `mdEvent` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="ad61e-121">Überprüfen Sie, ob `mdFieldDef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="ad61e-122">Überprüfen Sie, ob `mdSignature` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="ad61e-123">Überprüfen Sie, ob `mdModuleRef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="ad61e-124">Überprüfen Sie, ob `mdTypeSpec` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="ad61e-125">Überprüfen Sie, ob `mdImplMap` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="ad61e-126">Überprüfen Sie, ob `mdAssemblyRef` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="ad61e-127">Überprüfen Sie, ob `mdFile` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="ad61e-128">Überprüfen Sie, ob `mdExportedType` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="ad61e-129">Überprüfen Sie, ob `mdManifestResource` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="ad61e-130">Überprüfen Sie, ob `mdGenericParam` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="ad61e-131">Überprüfen Sie, ob `mdMethodSpec` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="ad61e-132">Überprüfen Sie, ob `mdGenericParamConstraint` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="ad61e-133">Überprüfen Sie, ob `mdAssembly` Token doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ad61e-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="ad61e-134">Überprüfen Sie auf Duplikate von `mdMemberRef`-, `mdTypeRef`-, `mdSignature`-, `mdTypeSpec`-und `mdMethodSpec`-Token.</span><span class="sxs-lookup"><span data-stu-id="ad61e-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad61e-135">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ad61e-135">Requirements</span></span>  
 <span data-ttu-id="ad61e-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad61e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad61e-137">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="ad61e-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ad61e-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad61e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad61e-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad61e-139">See also</span></span>

- [<span data-ttu-id="ad61e-140">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ad61e-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
