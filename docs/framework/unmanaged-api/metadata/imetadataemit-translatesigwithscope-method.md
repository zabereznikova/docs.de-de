---
title: IMetaDataEmit::TranslateSigWithScope-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.TranslateSigWithScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5127defc97423283b52b7b5bd8c6b7a31104fbc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="9957a-102">IMetaDataEmit::TranslateSigWithScope-Methode</span><span class="sxs-lookup"><span data-stu-id="9957a-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="9957a-103">Importiert eine Assembly in den aktuellen Bereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="9957a-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9957a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9957a-104">Syntax</span></span>  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9957a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9957a-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="9957a-106">[in] Die Schnittstelle für den Importassembly (wobei die Signatur definiert wird).</span><span class="sxs-lookup"><span data-stu-id="9957a-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="9957a-107">[in] Der Hash-Blob für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="9957a-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="9957a-108">[in] Die Anzahl der Bytes im `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="9957a-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="9957a-109">[in] Die Schnittstelle für den Importmetadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="9957a-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="9957a-110">[in] Die Signatur, die importiert werden.</span><span class="sxs-lookup"><span data-stu-id="9957a-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9957a-111">[in] Die Größe in Bytes, der `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="9957a-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="9957a-112">[in] Die Schnittstelle für die Assembly exportieren.</span><span class="sxs-lookup"><span data-stu-id="9957a-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="9957a-113">[in] Die Schnittstelle für den Exportmetadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="9957a-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="9957a-114">[out] Der Puffer, die übersetzte Signatur-Blob zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9957a-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="9957a-115">[in] Die Kapazität in Bytes, der `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="9957a-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="9957a-116">[out] Die Anzahl der tatsächlichen Bytes in der übersetzten Signatur.</span><span class="sxs-lookup"><span data-stu-id="9957a-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9957a-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9957a-117">Requirements</span></span>  
 <span data-ttu-id="9957a-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9957a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9957a-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9957a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9957a-120">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9957a-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9957a-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9957a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9957a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9957a-122">See Also</span></span>  
 [<span data-ttu-id="9957a-123">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9957a-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="9957a-124">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9957a-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="9957a-125">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9957a-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9957a-126">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9957a-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="9957a-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9957a-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
