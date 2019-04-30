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
ms.openlocfilehash: ba99d84686974b425bcdee0bbf4770e4843e1351
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992575"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="c0f5a-102">IMetaDataAssemblyImport::GetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="c0f5a-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="c0f5a-103">Ruft den Satz von Eigenschaften der Manifestressource mit der angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0f5a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c0f5a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0f5a-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="c0f5a-106">[in] Ein `mdManifestResource` Token, das die Ressource, für die zum Abrufen der Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="c0f5a-107">[out] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c0f5a-108">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c0f5a-109">[out] Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="c0f5a-110">[out] Ein Zeiger auf ein `mdFile` token oder ein `mdAssemblyRef` Token, die die Datei oder Assembly darstellt, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="c0f5a-111">[out] Ein Zeiger auf einen Wert, der den Offset vom Anfang der Ressource in der Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="c0f5a-112">[out] Ein Zeiger auf Flags, die beschreiben, die Metadaten, die auf eine Ressource angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="c0f5a-113">Der Wert des Flags ist eine Kombination aus einem oder mehreren [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="c0f5a-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f5a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0f5a-114">Requirements</span></span>  
 <span data-ttu-id="c0f5a-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0f5a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0f5a-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0f5a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0f5a-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c0f5a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0f5a-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0f5a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f5a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0f5a-119">See also</span></span>

- [<span data-ttu-id="c0f5a-120">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0f5a-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
