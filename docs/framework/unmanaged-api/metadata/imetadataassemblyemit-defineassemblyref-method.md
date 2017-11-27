---
title: IMetaDataAssemblyEmit::DefineAssemblyRef-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssemblyRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 074e589b84e21de4ec3bcc3c54a865297587d383
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="4e37b-102">IMetaDataAssemblyEmit::DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="4e37b-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="4e37b-103">Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="4e37b-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e37b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e37b-104">Syntax</span></span>  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e37b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e37b-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="4e37b-106">[in] Der öffentliche Schlüssel des Herausgebers der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4e37b-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="4e37b-107">Die Hilfsfunktion [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) dienen zum Abrufen des Hashs des öffentlichen Schlüssels an diesen Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="4e37b-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="4e37b-108">[in] Die Größe in Bytes des `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="4e37b-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e37b-109">[in] Der lesbare Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="4e37b-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="4e37b-110">Dieser Wert darf 1024 Zeichen nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="4e37b-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="4e37b-111">[in] Eine ASSEMBLYMETADATA-Instanz, die Version, Plattform und Gebietsschema-Informationen der referenzierten Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="4e37b-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="4e37b-112">[in] Der Hashwert der Daten die referenzierte Assembly zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4e37b-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="4e37b-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4e37b-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="4e37b-114">[in] Die Größe in Bytes des `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="4e37b-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="4e37b-115">[in] Eine bitweise Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte, die das Verhalten des Ausführungsmoduls beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="4e37b-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="4e37b-116">[out] Ein Zeiger auf das zurückgegebene `AssemblyRef` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="4e37b-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e37b-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e37b-117">Remarks</span></span>  
 <span data-ttu-id="4e37b-118">Eine `AssemblyRef` Metadatenstruktur muss definiert werden, für jede Assembly, die diese Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="4e37b-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="4e37b-119">Zur Laufzeit werden die Details einer referenzierten Assembly, das der Assemblyresolver mit Angabe übergeben, dass sie die Informationen "wie erstellt" darstellen.</span><span class="sxs-lookup"><span data-stu-id="4e37b-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="4e37b-120">Der Assemblyresolver wendet dann die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="4e37b-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e37b-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e37b-121">Requirements</span></span>  
 <span data-ttu-id="4e37b-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e37b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e37b-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4e37b-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e37b-124">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4e37b-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e37b-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e37b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e37b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e37b-126">See Also</span></span>  
 [<span data-ttu-id="4e37b-127">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e37b-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
