---
title: IMetaDataAssemblyEmit::SetAssemblyProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aab505700b669cae071420117abd71332f49d8b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="d83a5-102">IMetaDataAssemblyEmit::SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="d83a5-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="d83a5-103">Ändert die angegebene `Assembly`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="d83a5-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d83a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d83a5-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d83a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d83a5-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="d83a5-106">[in] Das Metadatentoken, der angibt, die `Assembly` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d83a5-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="d83a5-107">[in] Ein Zeiger auf den öffentlichen Schlüssel des Herausgebers der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d83a5-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="d83a5-108">[in] Die Größe in Bytes des `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="d83a5-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="d83a5-109">[in] Der Bezeichner für die Hash-Algorithmus verwendet, um die Assemblydateien hash.</span><span class="sxs-lookup"><span data-stu-id="d83a5-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="d83a5-110">[in] Der lesbare Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d83a5-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d83a5-111">[in] Ein Zeiger auf die ASSEMBLYMETADATA, Version, Plattform und Gebietsschema-Informationen für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="d83a5-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="d83a5-112">[in] Eine bitweise Kombination von [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) Werte, die verschiedene Attribute der Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="d83a5-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d83a5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d83a5-113">Remarks</span></span>  
 <span data-ttu-id="d83a5-114">Zum Erstellen einer `Assembly` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d83a5-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d83a5-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d83a5-115">Requirements</span></span>  
 <span data-ttu-id="d83a5-116">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d83a5-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d83a5-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d83a5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d83a5-118">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d83a5-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d83a5-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d83a5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83a5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d83a5-120">See Also</span></span>  
 [<span data-ttu-id="d83a5-121">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d83a5-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
