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
ms.openlocfilehash: 629e18b6cd2fd7910804ecc608a45d2406dddea1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007493"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="d13d2-102">CorTokenType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d13d2-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="d13d2-103">Gibt den Typ eines Metadatentokens an.</span><span class="sxs-lookup"><span data-stu-id="d13d2-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d13d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d13d2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="d13d2-105">Member</span><span class="sxs-lookup"><span data-stu-id="d13d2-105">Members</span></span>  
  
|<span data-ttu-id="d13d2-106">Member</span><span class="sxs-lookup"><span data-stu-id="d13d2-106">Member</span></span>|<span data-ttu-id="d13d2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d13d2-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="d13d2-108">Ein- `mdModule` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="d13d2-109">Ein- `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="d13d2-110">Ein- `mdTypeDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="d13d2-111">Ein- `mdFieldDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="d13d2-112">Ein- `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="d13d2-113">Ein- `mdParamDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="d13d2-114">Ein- `mdInterfaceImpl` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="d13d2-115">Ein- `mdMemberRef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="d13d2-116">Ein- `mdCustomAttribute` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="d13d2-117">Ein- `mdPermission` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="d13d2-118">Ein- `mdSignature` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="d13d2-119">Ein- `mdEvent` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="d13d2-120">Ein- `mdProperty` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="d13d2-121">Ein- `mdModuleRef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="d13d2-122">Ein- `mdTypeSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="d13d2-123">Ein- `mdAssembly` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="d13d2-124">Ein- `mdAssemblyRef` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="d13d2-125">Ein- `mdFile` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="d13d2-126">Ein- `mdExportedType` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="d13d2-127">Ein- `mdManifestResource` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="d13d2-128">Ein- `mdGenericParam` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="d13d2-129">Ein- `mdMethodSpec` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="d13d2-130">Ein- `mdGenericParamConstraint` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="d13d2-131">Ein- `mdString` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="d13d2-132">Ein- `mdName` Token.</span><span class="sxs-lookup"><span data-stu-id="d13d2-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="d13d2-133">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d13d2-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d13d2-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d13d2-134">Remarks</span></span>  
 <span data-ttu-id="d13d2-135">Jeder Wert entspricht dem Wert des obersten Bytes im entsprechenden Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="d13d2-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d13d2-136">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d13d2-136">Requirements</span></span>  
 <span data-ttu-id="d13d2-137">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d13d2-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d13d2-138">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="d13d2-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d13d2-139">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d13d2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13d2-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d13d2-140">See also</span></span>

- [<span data-ttu-id="d13d2-141">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d13d2-141">Metadata Enumerations</span></span>](metadata-enumerations.md)
