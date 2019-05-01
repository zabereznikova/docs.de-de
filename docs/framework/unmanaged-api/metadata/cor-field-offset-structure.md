---
title: COR_FIELD_OFFSET-Struktur
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 820c99de1bdb108a24203a3438b1709ca54490b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046188"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="ae09c-102">COR_FIELD_OFFSET-Struktur</span><span class="sxs-lookup"><span data-stu-id="ae09c-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="ae09c-103">Speichert den Offset des angegebenen Felds innerhalb einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="ae09c-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae09c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae09c-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="ae09c-105">Member</span><span class="sxs-lookup"><span data-stu-id="ae09c-105">Members</span></span>  
  
|<span data-ttu-id="ae09c-106">Member</span><span class="sxs-lookup"><span data-stu-id="ae09c-106">Member</span></span>|<span data-ttu-id="ae09c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae09c-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="ae09c-108">Ein `mdFieldDef` Metadatentoken, das Feld darstellt.</span><span class="sxs-lookup"><span data-stu-id="ae09c-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="ae09c-109">Das Feld uhrzeitabweichung innerhalb seiner Klasse.</span><span class="sxs-lookup"><span data-stu-id="ae09c-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae09c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae09c-110">Remarks</span></span>  
 <span data-ttu-id="ae09c-111">[IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) und [IMetaDataEmit:: SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) Methoden akzeptieren einen Parameter vom Typ `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="ae09c-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae09c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae09c-112">Requirements</span></span>  
 <span data-ttu-id="ae09c-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae09c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae09c-114">**Header:** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ae09c-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="ae09c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae09c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae09c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae09c-116">See also</span></span>

- [<span data-ttu-id="ae09c-117">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="ae09c-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="ae09c-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae09c-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ae09c-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae09c-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
