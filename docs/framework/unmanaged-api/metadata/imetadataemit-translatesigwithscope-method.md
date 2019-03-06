---
title: IMetaDataEmit::TranslateSigWithScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1243a5ed1a3b741f1691cc4f0847ddcf17ac9669
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478387"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="7d5fd-102">IMetaDataEmit::TranslateSigWithScope-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5fd-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="7d5fd-103">Importiert eine Assembly in den aktuellen Bereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d5fd-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7d5fd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d5fd-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="7d5fd-106">[in] Die Schnittstelle für den Importassembly (in dem die Signatur definiert ist).</span><span class="sxs-lookup"><span data-stu-id="7d5fd-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7d5fd-107">[in] Der Hash-Blob für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7d5fd-108">[in] Die Anzahl der Bytes im `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="7d5fd-109">[in] Die Schnittstelle für den Importmetadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="7d5fd-110">[in] Die Signatur, die importiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="7d5fd-111">[in] Die Größe in Bytes, des `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="7d5fd-112">[in] Die Schnittstelle für den Exportassembly.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="7d5fd-113">[in] Die Schnittstelle für den Exportmetadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="7d5fd-114">[out] Der Puffer, die den übersetzten Signatur-Blob zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="7d5fd-115">[in] Die Kapazität in Bytes, des `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="7d5fd-116">[out] Die Anzahl der tatsächlichen Bytes in der übersetzten Signatur.</span><span class="sxs-lookup"><span data-stu-id="7d5fd-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5fd-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d5fd-117">Requirements</span></span>  
 <span data-ttu-id="7d5fd-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d5fd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d5fd-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7d5fd-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d5fd-120">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7d5fd-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d5fd-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d5fd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5fd-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d5fd-122">See also</span></span>
- [<span data-ttu-id="7d5fd-123">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5fd-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="7d5fd-124">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5fd-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="7d5fd-125">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5fd-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7d5fd-126">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5fd-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="7d5fd-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5fd-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
