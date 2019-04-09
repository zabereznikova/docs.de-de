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
ms.openlocfilehash: d04f5589ecffbcde59a6ffbe4f3d6c5f0b1040cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074871"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="6b248-102">CorCheckDuplicatesFor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6b248-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="6b248-103">Gibt an, die Metadatentoken, die auf Duplikate überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="6b248-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b248-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b248-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6b248-105">Member</span><span class="sxs-lookup"><span data-stu-id="6b248-105">Members</span></span>  
  
|<span data-ttu-id="6b248-106">Member</span><span class="sxs-lookup"><span data-stu-id="6b248-106">Member</span></span>|<span data-ttu-id="6b248-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b248-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="6b248-108">Überprüfen Sie alle Metadatentoken für Duplikate an.</span><span class="sxs-lookup"><span data-stu-id="6b248-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="6b248-109">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b248-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="6b248-110">Metadatentoken für die Duplikate werden nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="6b248-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="6b248-111">Duplikate von `mdTypeDef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="6b248-112">Duplikate von `mdInterfaceImpl` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="6b248-113">Duplikate von `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="6b248-114">Duplikate von `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="6b248-115">Duplikate von `mdMemberRef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="6b248-116">Duplikate von `mdCustomAttribute` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="6b248-117">Duplikate von `mdParamDef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="6b248-118">Duplikate von `mdPermission` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="6b248-119">Duplikate von `mdProperty` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="6b248-120">Duplikate von `mdEvent` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="6b248-121">Duplikate von `mdFieldDef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="6b248-122">Duplikate von `mdSignature` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="6b248-123">Duplikate von `mdModuleRef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="6b248-124">Duplikate von `mdTypeSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="6b248-125">Duplikate von `mdImplMap` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="6b248-126">Duplikate von `mdAssemblyRef` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="6b248-127">Duplikate von `mdFile` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="6b248-128">Duplikate von `mdExportedType` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="6b248-129">Duplikate von `mdManifestResource` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="6b248-130">Duplikate von `mdGenericParam` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="6b248-131">Duplikate von `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="6b248-132">Duplikate von `mdGenericParamConstraint` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="6b248-133">Duplikate von `mdAssembly` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="6b248-134">Duplikate von `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, und `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="6b248-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b248-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b248-135">Requirements</span></span>  
 <span data-ttu-id="6b248-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b248-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b248-137">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6b248-137">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="6b248-138">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6b248-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b248-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b248-139">See also</span></span>

- [<span data-ttu-id="6b248-140">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="6b248-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
