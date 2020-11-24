---
title: CorNotificationForTokenMovement-Enumeration
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 0f9cb8db35a1669cead6f9f26c9a89e063628dd8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687670"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="6f28f-102">CorNotificationForTokenMovement-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6f28f-102">CorNotificationForTokenMovement Enumeration</span></span>

<span data-ttu-id="6f28f-103">Gibt die Benachrichtigungen an, die an den metadatenapi-Client gesendet werden, wenn eine Neuzuordnung eines Tokens auftritt.</span><span class="sxs-lookup"><span data-stu-id="6f28f-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f28f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f28f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="6f28f-105">Member</span><span class="sxs-lookup"><span data-stu-id="6f28f-105">Members</span></span>  
  
|<span data-ttu-id="6f28f-106">Member</span><span class="sxs-lookup"><span data-stu-id="6f28f-106">Member</span></span>|<span data-ttu-id="6f28f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6f28f-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="6f28f-108">Benachrichtigen, wenn-,-,- `mdTypeRef` `mdMethodDef` oder- `mdMemberRef` `mdFieldDef` Token verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="6f28f-109">Benachrichtigen, wenn ein beliebiges Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="6f28f-110">Nicht benachrichtigen, wenn Token verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="6f28f-111">Benachrichtigen, wenn ein `mdMethodDef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="6f28f-112">Benachrichtigen, wenn ein `mdMemberRef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="6f28f-113">Benachrichtigen, wenn ein `mdFieldDef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="6f28f-114">Benachrichtigen, wenn ein `mdTypeRef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="6f28f-115">Benachrichtigen, wenn ein `mdTypeDef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="6f28f-116">Benachrichtigen, wenn ein `mdParamDef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="6f28f-117">Benachrichtigen, wenn ein `mdInterfaceImpl` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="6f28f-118">Benachrichtigen, wenn ein `mdProperty` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="6f28f-119">Benachrichtigen, wenn ein `mdEvent` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="6f28f-120">Benachrichtigen, wenn ein `mdSignature` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="6f28f-121">Benachrichtigen, wenn ein `mdTypeSpec` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="6f28f-122">Benachrichtigen, wenn ein `mdCustomAttribute` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="6f28f-123">Benachrichtigen, wenn ein `mdSecurityValue` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="6f28f-124">Benachrichtigen, wenn ein `mdPermission` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="6f28f-125">Benachrichtigen, wenn ein `mdModuleRef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="6f28f-126">Benachrichtigen, wenn ein `mdNameSpace` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="6f28f-127">Benachrichtigen, wenn ein `mdAssemblyRef` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="6f28f-128">Benachrichtigen, wenn ein `mdFile` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="6f28f-129">Benachrichtigen, wenn ein `mdExportedType` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="6f28f-130">Benachrichtigen, wenn ein `mdManifestResource` Token verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="6f28f-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f28f-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f28f-131">Remarks</span></span>  

 <span data-ttu-id="6f28f-132">Ein Token kann während einer Metadatenzusammenführung neu zugeordnet (d. h. verschoben) werden.</span><span class="sxs-lookup"><span data-stu-id="6f28f-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f28f-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f28f-133">Requirements</span></span>  

 <span data-ttu-id="6f28f-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f28f-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f28f-135">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="6f28f-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6f28f-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f28f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f28f-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f28f-137">See also</span></span>

- [<span data-ttu-id="6f28f-138">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="6f28f-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
