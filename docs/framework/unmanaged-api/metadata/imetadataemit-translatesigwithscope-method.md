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
ms.openlocfilehash: 2662af41fbd2cdc3ce8a6df1e036dfc5b22ff6a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175550"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="f1310-102">IMetaDataEmit::TranslateSigWithScope-Methode</span><span class="sxs-lookup"><span data-stu-id="f1310-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="f1310-103">Importiert eine Assembly in den aktuellen Bereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="f1310-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1310-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1310-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f1310-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1310-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="f1310-106">[in] Die Schnittstelle für die Importassembly (wobei die Signatur definiert ist).</span><span class="sxs-lookup"><span data-stu-id="f1310-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f1310-107">[in] Das Hash-Blob für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="f1310-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f1310-108">[in] Die Anzahl der `pbHashValue`Bytes in .</span><span class="sxs-lookup"><span data-stu-id="f1310-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="f1310-109">[in] Die Schnittstelle für den Importmetadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="f1310-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="f1310-110">[in] Die zu importierende Signatur.</span><span class="sxs-lookup"><span data-stu-id="f1310-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f1310-111">[in] Die Größe von in `pbSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="f1310-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="f1310-112">[in] Die Schnittstelle für die Exportassembly.</span><span class="sxs-lookup"><span data-stu-id="f1310-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="f1310-113">[in] Die Schnittstelle für den Export metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="f1310-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="f1310-114">[out] Der Puffer, der das übersetzte Signaturblob enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="f1310-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="f1310-115">[in] Die Kapazität (in `pvTranslatedSig`Bytes) von .</span><span class="sxs-lookup"><span data-stu-id="f1310-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="f1310-116">[out] Die Anzahl der tatsächlichen Bytes in der übersetzten Signatur.</span><span class="sxs-lookup"><span data-stu-id="f1310-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1310-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1310-117">Requirements</span></span>  
 <span data-ttu-id="f1310-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1310-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1310-119">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1310-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1310-120">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f1310-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1310-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1310-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1310-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1310-122">See also</span></span>

- [<span data-ttu-id="f1310-123">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1310-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f1310-124">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1310-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="f1310-125">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1310-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f1310-126">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1310-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="f1310-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1310-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
