---
title: IMetaDataAssemblyImport::GetManifestResourceProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07237794ca45b16b1ae1ca95b1d62889f095350f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448158"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="6f4ea-102">IMetaDataAssemblyImport::GetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="6f4ea-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="6f4ea-103">Ruft den Satz von Eigenschaften der Manifestressource mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f4ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f4ea-104">Syntax</span></span>  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f4ea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f4ea-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="6f4ea-106">[in] Ein `mdManifestResource` Token, das die Ressource für das Abrufen der Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="6f4ea-107">[out] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6f4ea-108">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="6f4ea-109">[out] Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="6f4ea-110">[out] Ein Zeiger auf ein `mdFile` token oder ein `mdAssemblyRef` Token, das die Datei bzw. die Assembly darstellt, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="6f4ea-111">[out] Ein Zeiger auf einen Wert, der den Offset vom Anfang der Ressource in der Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="6f4ea-112">[out] Ein Zeiger auf die Flags, die auf eine Ressource angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="6f4ea-113">Der Wert des Flags ist eine Kombination aus einem oder mehreren [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="6f4ea-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f4ea-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f4ea-114">Requirements</span></span>  
 <span data-ttu-id="6f4ea-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f4ea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f4ea-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6f4ea-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f4ea-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6f4ea-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6f4ea-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f4ea-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f4ea-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f4ea-119">See Also</span></span>  
 [<span data-ttu-id="6f4ea-120">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f4ea-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
