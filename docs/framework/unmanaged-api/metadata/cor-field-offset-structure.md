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
ms.openlocfilehash: 1a8ab5aa5909af60089d5e4cc8092e15bc75e8cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724181"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="c6ea5-102">COR_FIELD_OFFSET-Struktur</span><span class="sxs-lookup"><span data-stu-id="c6ea5-102">COR_FIELD_OFFSET Structure</span></span>

<span data-ttu-id="c6ea5-103">Speichert den Offset des angegebenen Felds innerhalb einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="c6ea5-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ea5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6ea5-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="c6ea5-105">Member</span><span class="sxs-lookup"><span data-stu-id="c6ea5-105">Members</span></span>  
  
|<span data-ttu-id="c6ea5-106">Member</span><span class="sxs-lookup"><span data-stu-id="c6ea5-106">Member</span></span>|<span data-ttu-id="c6ea5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c6ea5-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="c6ea5-108">Ein `mdFieldDef` Metadatentoken, das das Feld darstellt.</span><span class="sxs-lookup"><span data-stu-id="c6ea5-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="c6ea5-109">Der Offset des Felds in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="c6ea5-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6ea5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6ea5-110">Remarks</span></span>  

 <span data-ttu-id="c6ea5-111">Die [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) -Methode und die [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) -Methode übernehmen einen Parameter vom Typ `COR_FIELD_OFFSET` .</span><span class="sxs-lookup"><span data-stu-id="c6ea5-111">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ea5-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c6ea5-112">Requirements</span></span>  

 <span data-ttu-id="c6ea5-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ea5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ea5-114">**Header:** Corhdr. h, Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="c6ea5-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="c6ea5-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6ea5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ea5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6ea5-116">See also</span></span>

- [<span data-ttu-id="c6ea5-117">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="c6ea5-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="c6ea5-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6ea5-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c6ea5-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6ea5-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
