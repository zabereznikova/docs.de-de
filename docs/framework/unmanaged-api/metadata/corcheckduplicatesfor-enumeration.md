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
ms.openlocfilehash: 2985c419b25b8bf76df8fee0f0f37ba9ebee3df7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007900"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="decf7-102">CorCheckDuplicatesFor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="decf7-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="decf7-103">Gibt die Metadatentoken an, die auf Duplikate geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="decf7-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="decf7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="decf7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="decf7-105">Member</span><span class="sxs-lookup"><span data-stu-id="decf7-105">Members</span></span>  
  
|<span data-ttu-id="decf7-106">Member</span><span class="sxs-lookup"><span data-stu-id="decf7-106">Member</span></span>|<span data-ttu-id="decf7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="decf7-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="decf7-108">Überprüfen Sie alle Metadatentoken auf Duplikate.</span><span class="sxs-lookup"><span data-stu-id="decf7-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="decf7-109">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="decf7-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="decf7-110">Überprüfen Sie die Metadatentoken nicht auf Duplikate.</span><span class="sxs-lookup"><span data-stu-id="decf7-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="decf7-111">Überprüfen Sie auf Duplikate von `mdTypeDef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="decf7-112">Überprüfen Sie auf Duplikate von `mdInterfaceImpl` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="decf7-113">Überprüfen Sie auf Duplikate von `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="decf7-114">Überprüfen Sie auf Duplikate von `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="decf7-115">Überprüfen Sie auf Duplikate von `mdMemberRef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="decf7-116">Überprüfen Sie auf Duplikate von `mdCustomAttribute` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="decf7-117">Überprüfen Sie auf Duplikate von `mdParamDef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="decf7-118">Überprüfen Sie auf Duplikate von `mdPermission` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="decf7-119">Überprüfen Sie auf Duplikate von `mdProperty` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="decf7-120">Überprüfen Sie auf Duplikate von `mdEvent` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="decf7-121">Überprüfen Sie auf Duplikate von `mdFieldDef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="decf7-122">Überprüfen Sie auf Duplikate von `mdSignature` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="decf7-123">Überprüfen Sie auf Duplikate von `mdModuleRef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="decf7-124">Überprüfen Sie auf Duplikate von `mdTypeSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="decf7-125">Überprüfen Sie auf Duplikate von `mdImplMap` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="decf7-126">Überprüfen Sie auf Duplikate von `mdAssemblyRef` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="decf7-127">Überprüfen Sie auf Duplikate von `mdFile` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="decf7-128">Überprüfen Sie auf Duplikate von `mdExportedType` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="decf7-129">Überprüfen Sie auf Duplikate von `mdManifestResource` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="decf7-130">Überprüfen Sie auf Duplikate von `mdGenericParam` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="decf7-131">Überprüfen Sie auf Duplikate von `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="decf7-132">Überprüfen Sie auf Duplikate von `mdGenericParamConstraint` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="decf7-133">Überprüfen Sie auf Duplikate von `mdAssembly` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="decf7-134">Überprüfen Sie auf Duplikate von `mdMemberRef` `mdTypeRef` -,-,-, `mdSignature` `mdTypeSpec` -und- `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="decf7-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="decf7-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="decf7-135">Requirements</span></span>  
 <span data-ttu-id="decf7-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="decf7-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="decf7-137">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="decf7-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="decf7-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="decf7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="decf7-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="decf7-139">See also</span></span>

- [<span data-ttu-id="decf7-140">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="decf7-140">Metadata Enumerations</span></span>](metadata-enumerations.md)
