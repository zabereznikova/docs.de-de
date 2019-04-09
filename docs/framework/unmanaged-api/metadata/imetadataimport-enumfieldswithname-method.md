---
title: IMetaDataImport::EnumFieldsWithName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf624695136a9397937f05b28dec18493c8e12d7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153659"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="07802-102">IMetaDataImport::EnumFieldsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="07802-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="07802-103">Zählt FieldDef-Token des angegebenen Typs mit dem angegebenen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="07802-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07802-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07802-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07802-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07802-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="07802-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="07802-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="07802-107">[in] Das Token des Typs, deren Felder sind, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="07802-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="07802-108">[in] Der Name des Felds, das den Bereich der Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="07802-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="07802-109">[out] Array zum Speichern der FieldDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07802-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="07802-110">[in] Die maximale Größe des `rFields`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="07802-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="07802-111">[out] Die tatsächliche Anzahl der zurückgegebenen FieldDef-Token `rFields`.</span><span class="sxs-lookup"><span data-stu-id="07802-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07802-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07802-112">Remarks</span></span>  
 <span data-ttu-id="07802-113">Im Gegensatz zu [IMetaDataImport:: EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` verwirft alle Feld-Token, die nicht mit den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="07802-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07802-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07802-114">Return Value</span></span>  
  
|<span data-ttu-id="07802-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07802-115">HRESULT</span></span>|<span data-ttu-id="07802-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07802-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumFieldsWithName` <span data-ttu-id="07802-117">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="07802-117">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="07802-118">Es gibt keine Felder aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="07802-118">There are no fields to enumerate.</span></span> <span data-ttu-id="07802-119">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="07802-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07802-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07802-120">Requirements</span></span>  
 <span data-ttu-id="07802-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07802-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07802-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07802-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07802-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="07802-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="07802-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="07802-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07802-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07802-125">See also</span></span>

- [<span data-ttu-id="07802-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07802-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="07802-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07802-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
