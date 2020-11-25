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
ms.openlocfilehash: 0a254587282dea43a3507fbbeca35bd7aa9604f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711571"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="a920d-102">IMetaDataImport::EnumFieldsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="a920d-102">IMetaDataImport::EnumFieldsWithName Method</span></span>

<span data-ttu-id="a920d-103">Zählt FieldDef-Token des angegebenen Typs mit dem angegebenen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="a920d-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a920d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a920d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a920d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a920d-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a920d-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a920d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="a920d-107">in Das Token des Typs, dessen Felder aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a920d-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="a920d-108">in Der Feldname, der den Bereich der Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="a920d-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="a920d-109">vorgenommen Das Array, das zum Speichern der FieldDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a920d-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a920d-110">[in] Die maximale Größe des `rFields`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a920d-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a920d-111">vorgenommen Die tatsächliche Anzahl der in zurückgegebenen FieldDef-Token `rFields` .</span><span class="sxs-lookup"><span data-stu-id="a920d-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a920d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a920d-112">Remarks</span></span>  

 <span data-ttu-id="a920d-113">Im Gegensatz zu [IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md) `EnumFieldsWithName` verwirft alle Feld Token, die nicht über den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="a920d-113">Unlike [IMetaDataImport::EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a920d-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a920d-114">Return Value</span></span>  
  
|<span data-ttu-id="a920d-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a920d-115">HRESULT</span></span>|<span data-ttu-id="a920d-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a920d-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a920d-117">`EnumFieldsWithName` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a920d-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a920d-118">Es sind keine Felder zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a920d-118">There are no fields to enumerate.</span></span> <span data-ttu-id="a920d-119">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a920d-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a920d-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a920d-120">Requirements</span></span>  

 <span data-ttu-id="a920d-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a920d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a920d-122">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a920d-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a920d-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a920d-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a920d-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a920d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a920d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a920d-125">See also</span></span>

- [<span data-ttu-id="a920d-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a920d-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a920d-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a920d-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
