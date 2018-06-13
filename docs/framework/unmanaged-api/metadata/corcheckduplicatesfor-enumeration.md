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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9cdb1570b682088e92ff7c7a78d84259d02d8512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444502"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="efbfc-102">CorCheckDuplicatesFor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="efbfc-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="efbfc-103">Gibt die Metadatentoken, die auf Duplikate überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="efbfc-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efbfc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efbfc-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="efbfc-105">Member</span><span class="sxs-lookup"><span data-stu-id="efbfc-105">Members</span></span>  
  
|<span data-ttu-id="efbfc-106">Member</span><span class="sxs-lookup"><span data-stu-id="efbfc-106">Member</span></span>|<span data-ttu-id="efbfc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efbfc-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="efbfc-108">Überprüfen Sie alle Metadatentoken für Duplikate an.</span><span class="sxs-lookup"><span data-stu-id="efbfc-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="efbfc-109">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="efbfc-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="efbfc-110">Überprüfen Sie die Metadatentoken für die Duplikate nicht.</span><span class="sxs-lookup"><span data-stu-id="efbfc-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="efbfc-111">Überprüfen Sie nach doppelten Einträgen `mdTypeDef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="efbfc-112">Überprüfen Sie nach doppelten Einträgen `mdInterfaceImpl` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="efbfc-113">Überprüfen Sie nach doppelten Einträgen `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="efbfc-114">Überprüfen Sie nach doppelten Einträgen `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="efbfc-115">Überprüfen Sie nach doppelten Einträgen `mdMemberRef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="efbfc-116">Überprüfen Sie nach doppelten Einträgen `mdCustomAttribute` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="efbfc-117">Überprüfen Sie nach doppelten Einträgen `mdParamDef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="efbfc-118">Überprüfen Sie nach doppelten Einträgen `mdPermission` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="efbfc-119">Überprüfen Sie nach doppelten Einträgen `mdProperty` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="efbfc-120">Überprüfen Sie nach doppelten Einträgen `mdEvent` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="efbfc-121">Überprüfen Sie nach doppelten Einträgen `mdFieldDef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="efbfc-122">Überprüfen Sie nach doppelten Einträgen `mdSignature` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="efbfc-123">Überprüfen Sie nach doppelten Einträgen `mdModuleRef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="efbfc-124">Überprüfen Sie nach doppelten Einträgen `mdTypeSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="efbfc-125">Überprüfen Sie nach doppelten Einträgen `mdImplMap` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="efbfc-126">Überprüfen Sie nach doppelten Einträgen `mdAssemblyRef` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="efbfc-127">Überprüfen Sie nach doppelten Einträgen `mdFile` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="efbfc-128">Überprüfen Sie nach doppelten Einträgen `mdExportedType` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="efbfc-129">Überprüfen Sie nach doppelten Einträgen `mdManifestResource` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="efbfc-130">Überprüfen Sie nach doppelten Einträgen `mdGenericParam` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="efbfc-131">Überprüfen Sie nach doppelten Einträgen `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="efbfc-132">Überprüfen Sie nach doppelten Einträgen `mdGenericParamConstraint` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="efbfc-133">Überprüfen Sie nach doppelten Einträgen `mdAssembly` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="efbfc-134">Überprüfen Sie nach doppelten Einträgen `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, und `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="efbfc-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efbfc-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="efbfc-135">Requirements</span></span>  
 <span data-ttu-id="efbfc-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efbfc-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efbfc-137">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="efbfc-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="efbfc-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efbfc-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efbfc-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efbfc-139">See Also</span></span>  
 [<span data-ttu-id="efbfc-140">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="efbfc-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
