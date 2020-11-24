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
ms.openlocfilehash: ba53ff30f0b6d0ae7fed7db422b7c0a242204a2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689432"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="5d990-102">IMetaDataAssemblyEmit::DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="5d990-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>

<span data-ttu-id="5d990-103">Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="5d990-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d990-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d990-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5d990-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d990-105">Parameters</span></span>  

 `pbPublicKeyOrToken`  
 <span data-ttu-id="5d990-106">in Der öffentliche Schlüssel des Verlegers der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5d990-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="5d990-107">Die Hilfsfunktion [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) kann verwendet werden, um den Hash des öffentlichen Schlüssels zu erhalten, der als dieser Parameter übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d990-107">The helper function [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="5d990-108">in Die Größe von in Bytes `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="5d990-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="5d990-109">in Der lesbare Textname der Assembly.</span><span class="sxs-lookup"><span data-stu-id="5d990-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="5d990-110">Dieser Wert darf nicht länger als 1024 Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="5d990-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5d990-111">in Eine ASSEMBLYMETADATA-Instanz, die die Informationen zu Version, Plattform und Gebiets Schema der Assembly enthält, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5d990-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="5d990-112">in Die der referenzierten Assembly zugeordneten Hashdaten.</span><span class="sxs-lookup"><span data-stu-id="5d990-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="5d990-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5d990-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="5d990-114">in Die Größe von in Bytes `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="5d990-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="5d990-115">in Eine bitweise Kombination von [CorAssemblyFlags](corassemblyflags-enumeration.md) -Werten, die das Verhalten der Ausführungs-Engine beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="5d990-115">[in] A bitwise combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="5d990-116">vorgenommen Ein Zeiger auf das zurückgegebene Metadatentoken `AssemblyRef` .</span><span class="sxs-lookup"><span data-stu-id="5d990-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d990-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d990-117">Remarks</span></span>  

 <span data-ttu-id="5d990-118">`AssemblyRef`Für jede Assembly, auf die diese Assembly verweist, muss eine Metadatenstruktur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d990-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="5d990-119">Zur Laufzeit werden die Details einer Assembly, auf die verwiesen wird, an den Assemblyresolver übermittelt, die darauf hinweist, dass Sie die "als erstellt"-Informationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="5d990-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="5d990-120">Der Assemblyresolver wendet dann die Richtlinie an</span><span class="sxs-lookup"><span data-stu-id="5d990-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d990-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5d990-121">Requirements</span></span>  

 <span data-ttu-id="5d990-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d990-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d990-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5d990-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d990-124">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d990-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d990-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d990-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d990-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d990-126">See also</span></span>

- [<span data-ttu-id="5d990-127">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d990-127">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
