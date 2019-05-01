---
title: CorTokenType-Enumeration
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b33b50e53c454f2b62253d12943ea044240d8cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045200"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="428b2-102">CorTokenType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="428b2-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="428b2-103">Gibt den Typ von einem Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="428b2-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="428b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="428b2-104">Syntax</span></span>  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="428b2-105">Member</span><span class="sxs-lookup"><span data-stu-id="428b2-105">Members</span></span>  
  
|<span data-ttu-id="428b2-106">Member</span><span class="sxs-lookup"><span data-stu-id="428b2-106">Member</span></span>|<span data-ttu-id="428b2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="428b2-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="428b2-108">Ein `mdModule` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="428b2-109">Ein `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="428b2-110">Ein `mdTypeDef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="428b2-111">Ein `mdFieldDef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="428b2-112">Ein `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="428b2-113">Ein `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="428b2-114">Ein `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="428b2-115">Ein `mdMemberRef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="428b2-116">Ein `mdCustomAttribute` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="428b2-117">Ein `mdPermission` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="428b2-118">Ein `mdSignature` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="428b2-119">Ein `mdEvent` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="428b2-120">Ein `mdProperty` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="428b2-121">Ein `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="428b2-122">Ein `mdTypeSpec` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="428b2-123">Ein `mdAssembly` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="428b2-124">Ein `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="428b2-125">Ein `mdFile` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="428b2-126">Ein `mdExportedType` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="428b2-127">Ein `mdManifestResource` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="428b2-128">Ein `mdGenericParam` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="428b2-129">Ein `mdMethodSpec` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="428b2-130">Ein `mdGenericParamConstraint` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="428b2-131">Ein `mdString` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="428b2-132">Ein `mdName` token.</span><span class="sxs-lookup"><span data-stu-id="428b2-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="428b2-133">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="428b2-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="428b2-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="428b2-134">Remarks</span></span>  
 <span data-ttu-id="428b2-135">Jeder Wert ist gleich dem Wert, der das oberste Byte in den entsprechenden Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="428b2-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="428b2-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="428b2-136">Requirements</span></span>  
 <span data-ttu-id="428b2-137">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="428b2-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="428b2-138">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="428b2-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="428b2-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="428b2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428b2-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="428b2-140">See also</span></span>

- [<span data-ttu-id="428b2-141">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="428b2-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
