---
title: IMetaDataAssemblyImport::GetFileProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c4ca64d4781f0cc228c0af7f2ae772098d2f164a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="4b845-102">IMetaDataAssemblyImport::GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4b845-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="4b845-103">Ruft die Eigenschaften der Datei mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="4b845-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b845-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b845-104">Syntax</span></span>  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b845-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b845-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="4b845-106">[in] Die `mdFile` Metadatentoken, das die Datei für das Abrufen der Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b845-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="4b845-107">[out] Der einfache Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="4b845-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4b845-108">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="4b845-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4b845-109">[out] Die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="4b845-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="4b845-110">[out] Ein Zeiger auf den Hashwert.</span><span class="sxs-lookup"><span data-stu-id="4b845-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="4b845-111">Dies ist der Hash, mit dem SHA-1-Algorithmus, der Datei.</span><span class="sxs-lookup"><span data-stu-id="4b845-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="4b845-112">[out] Die Anzahl der Breitzeichen in den zurückgegebenen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="4b845-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="4b845-113">[out] Ein Zeiger auf die Flags, die auf eine Datei angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4b845-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="4b845-114">Der Wert des Flags ist eine Kombination aus einem oder mehreren [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="4b845-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b845-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b845-115">Requirements</span></span>  
 <span data-ttu-id="4b845-116">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b845-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b845-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b845-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b845-118">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4b845-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b845-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b845-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b845-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b845-120">See Also</span></span>  
 [<span data-ttu-id="4b845-121">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b845-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
