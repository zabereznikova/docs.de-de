---
title: IMetaDataAssemblyEmit::DefineManifestResource-Methode
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
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a435c946e13950faad7545e3da78ce373ee7fa0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="03922-102">IMetaDataAssemblyEmit::DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="03922-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="03922-103">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="03922-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03922-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03922-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03922-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="03922-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="03922-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="03922-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="03922-107">[in] Ein Metadatentoken des Typs `mdtFile` oder `mdtAssemblyRef` , der der Ressourcenanbieter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="03922-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="03922-108">Ein NULL-Wert gibt an, dass die Datei, in der die Metadaten eingebettet ist, der Ressourcenanbieter ist.</span><span class="sxs-lookup"><span data-stu-id="03922-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="03922-109">[in] Der Offset auf den Anfang der Ressource in der Datei.</span><span class="sxs-lookup"><span data-stu-id="03922-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="03922-110">Für Ressourcen in eigenständigen Dateien wird dies immer 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="03922-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="03922-111">Wenn die Ressource in einer PE (portable ausführbare) Datei eingebettet ist, ist dies ein Offset der Ressource-BLOB, das an die in der Headerdatei cor.h angegebenen Position beginnt.</span><span class="sxs-lookup"><span data-stu-id="03922-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="03922-112">[in] Eine bitweise Kombination der Flagwerte, die eigenschafteneinstellungen für die in der Ressourcendefinition angeben.</span><span class="sxs-lookup"><span data-stu-id="03922-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="03922-113">[out] Ein Zeiger auf die zurückgegebenen Metadaten-Token.</span><span class="sxs-lookup"><span data-stu-id="03922-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03922-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03922-114">Remarks</span></span>  
 <span data-ttu-id="03922-115">Eine `ManifestResource` Metadatenstruktur muss definiert werden, für jede Ressource, die in der Assembly aneinander gehängt Dateien implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="03922-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03922-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03922-116">Requirements</span></span>  
 <span data-ttu-id="03922-117">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03922-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03922-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="03922-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03922-119">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="03922-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03922-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03922-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03922-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03922-121">See Also</span></span>  
 [<span data-ttu-id="03922-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03922-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
