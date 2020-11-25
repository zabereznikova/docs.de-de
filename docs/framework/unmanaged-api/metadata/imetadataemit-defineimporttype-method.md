---
title: IMetaDataEmit::DefineImportType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 94ce4443be210fdfeb1bab197c3e603255e1cc4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723245"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="ffa78-102">IMetaDataEmit::DefineImportType-Methode</span><span class="sxs-lookup"><span data-stu-id="ffa78-102">IMetaDataEmit::DefineImportType Method</span></span>

<span data-ttu-id="ffa78-103">Erstellt einen Verweis auf den angegebenen Typ, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.</span><span class="sxs-lookup"><span data-stu-id="ffa78-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffa78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ffa78-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffa78-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ffa78-105">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="ffa78-106">in Eine [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus der der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ffa78-106">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ffa78-107">in Ein Array, das den Hash für die durch angegebene Assembly enthält `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="ffa78-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ffa78-108">[in] Die Anzahl der Bytes im `pbHashValue`-Array.</span><span class="sxs-lookup"><span data-stu-id="ffa78-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="ffa78-109">in Eine [IMetaDataImport](imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ffa78-109">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="ffa78-110">in Ein `mdTypeDef` Token, das den Zieltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="ffa78-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="ffa78-111">in Eine [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in die der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ffa78-111">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="ffa78-112">vorgenommen Das `mdTypeRef` Token, das im aktuellen Gültigkeitsbereich für den Typverweis definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ffa78-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffa78-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ffa78-113">Remarks</span></span>  

 <span data-ttu-id="ffa78-114">Vor dem Aufrufen der [IMetaDataEmit::D efineimportmember](imetadataemit-defineimportmember-method.md) -Methode können Sie mit der `DefineImportType` -Methode einen Typverweis im aktuellen Gültigkeitsbereich für die übergeordnete Klasse oder übergeordnete Schnittstelle des Members erstellen.</span><span class="sxs-lookup"><span data-stu-id="ffa78-114">Prior to calling the [IMetaDataEmit::DefineImportMember](imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffa78-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ffa78-115">Requirements</span></span>  

 <span data-ttu-id="ffa78-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffa78-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa78-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ffa78-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ffa78-118">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ffa78-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffa78-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa78-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa78-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ffa78-120">See also</span></span>

- [<span data-ttu-id="ffa78-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffa78-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ffa78-122">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffa78-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
