---
title: IMetaDataAssemblyEmit::DefineAssemblyRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c150f4bda901627fc21ed54926c3cf959bb829a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776300"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="86878-102">IMetaDataAssemblyEmit::DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="86878-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="86878-103">Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="86878-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86878-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="86878-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="86878-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="86878-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="86878-106">[in] Der öffentliche Schlüssel des Herausgebers der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="86878-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="86878-107">Die Hilfsfunktion [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) kann verwendet werden, um den Hash des öffentlichen Schlüssels, der als dieser Parameter übergeben zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86878-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="86878-108">[in] Die Größe in Bytes der `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="86878-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="86878-109">[in] Der Benutzer lesbarer Textname der Assembly.</span><span class="sxs-lookup"><span data-stu-id="86878-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="86878-110">Dieser Wert darf 1024 Zeichen nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="86878-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="86878-111">[in] Eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema-Informationen der referenzierten Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="86878-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="86878-112">[in] Die Hashdaten, das die referenzierte Assembly zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="86878-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="86878-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="86878-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="86878-114">[in] Die Größe in Bytes der `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="86878-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="86878-115">[in] Eine bitweise Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte, die das Verhalten von der ausführungs-Engine zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="86878-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="86878-116">[out] Ein Zeiger auf das zurückgegebene `AssemblyRef` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="86878-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86878-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86878-117">Remarks</span></span>  
 <span data-ttu-id="86878-118">Eine `AssemblyRef` Metadatenstruktur muss definiert werden, für jede Assembly, die diese Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="86878-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="86878-119">Zur Laufzeit werden die Details einer referenzierten Assembly auf der Assemblyresolver mit einem Hinweis übergeben, dass sie die "wie erstellt" Informationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="86878-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="86878-120">Der Assemblyresolver wendet dann die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="86878-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86878-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86878-121">Requirements</span></span>  
 <span data-ttu-id="86878-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86878-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86878-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86878-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86878-124">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="86878-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86878-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86878-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86878-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86878-126">See also</span></span>

- [<span data-ttu-id="86878-127">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86878-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
