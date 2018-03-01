---
title: IMetaDataAssemblyImport::GetAssemblyProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6e99474fea329f53286d698d0e1a302909d5cc65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="def32-102">IMetaDataAssemblyImport::GetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="def32-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="def32-103">Ruft den Satz von Eigenschaften für die Assembly mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="def32-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="def32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="def32-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="def32-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="def32-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="def32-106">[in].</span><span class="sxs-lookup"><span data-stu-id="def32-106">[in].</span></span> <span data-ttu-id="def32-107">Die `mdAssembly` Metadatentoken, das die Assembly für das Abrufen der Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="def32-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="def32-108">[out] Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="def32-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="def32-109">[out] Die Anzahl der Bytes in den zurückgegebenen öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="def32-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="def32-110">[out] Ein Zeiger auf den Algorithmus zum Hashen der Dateien in der Assembly verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="def32-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="def32-111">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="def32-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="def32-112">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="def32-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="def32-113">[out] Die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="def32-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="def32-114">[out] Ein Zeiger auf ein ASSEMBLYMETADATA-Struktur, die die Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="def32-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="def32-115">[out] Flags, die auf eine Assembly angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="def32-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="def32-116">Dieser Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="def32-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="def32-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="def32-117">Requirements</span></span>  
 <span data-ttu-id="def32-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="def32-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="def32-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="def32-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="def32-120">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="def32-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="def32-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="def32-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def32-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="def32-122">See Also</span></span>  
 [<span data-ttu-id="def32-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="def32-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
