---
title: IMetaDataAssemblyImport::GetExportedTypeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91b1e4469f07954dc433769911c78d72bb3c36cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904981"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="4b205-102">IMetaDataAssemblyImport::GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4b205-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="4b205-103">Ruft den Satz von Eigenschaften des exportierten Typs mit der angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="4b205-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b205-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b205-104">Syntax</span></span>  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b205-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b205-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="4b205-106">[in] Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b205-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="4b205-107">[out] Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="4b205-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4b205-108">[in] Die Größe in Breitzeichen, der `szName`.</span><span class="sxs-lookup"><span data-stu-id="4b205-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4b205-109">[out] Die Anzahl der Breitzeichen, die tatsächlich zurückgegeben. `szName`</span><span class="sxs-lookup"><span data-stu-id="4b205-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="4b205-110">[out] Ein `mdFile`, `mdAssemblyRef`, oder `mdExportedType` Metadatentoken, das enthält oder erlaubt den Zugriff auf die Eigenschaften des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="4b205-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="4b205-111">[out] Ein Zeiger auf ein `mdTypeDef` Token, das einen Typ in der Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b205-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="4b205-112">[out] Ein Zeiger auf die Flags, die in den exportierten Typ angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4b205-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="4b205-113">Der Wert des Flags kann sein, eine oder mehrere [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="4b205-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b205-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b205-114">Requirements</span></span>  
 <span data-ttu-id="4b205-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b205-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b205-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b205-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b205-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4b205-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b205-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b205-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b205-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b205-119">See also</span></span>

- [<span data-ttu-id="4b205-120">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b205-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
