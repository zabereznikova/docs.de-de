---
title: IMetaDataAssemblyEmit::DefineManifestResource-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="fbb3d-102">IMetaDataAssemblyEmit::DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="fbb3d-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="fbb3d-103">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbb3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbb3d-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fbb3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fbb3d-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="fbb3d-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="fbb3d-107">[in] Ein Metadatentoken des Typs `mdtFile` oder `mdtAssemblyRef` , der der Ressourcenanbieter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="fbb3d-108">Ein NULL-Wert gibt an, dass die Datei, in der die Metadaten eingebettet ist, der Ressourcenanbieter ist.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="fbb3d-109">[in] Der Offset auf den Anfang der Ressource in der Datei.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="fbb3d-110">Für Ressourcen in eigenständigen Dateien wird dies immer 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="fbb3d-111">Wenn die Ressource in einer PE (portable ausführbare) Datei eingebettet ist, ist dies ein Offset der Ressource-BLOB, das an die in der Headerdatei cor.h angegebenen Position beginnt.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="fbb3d-112">[in] Eine bitweise Kombination der Flagwerte, die eigenschafteneinstellungen für die in der Ressourcendefinition angeben.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="fbb3d-113">[out] Ein Zeiger auf die zurückgegebenen Metadaten-Token.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbb3d-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fbb3d-114">Remarks</span></span>  
 <span data-ttu-id="fbb3d-115">Eine `ManifestResource` Metadatenstruktur muss definiert werden, für jede Ressource, die in der Assembly aneinander gehängt Dateien implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="fbb3d-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbb3d-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbb3d-116">Requirements</span></span>  
 <span data-ttu-id="fbb3d-117">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbb3d-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbb3d-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fbb3d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fbb3d-119">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="fbb3d-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fbb3d-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbb3d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbb3d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbb3d-121">See Also</span></span>  
 [<span data-ttu-id="fbb3d-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbb3d-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
