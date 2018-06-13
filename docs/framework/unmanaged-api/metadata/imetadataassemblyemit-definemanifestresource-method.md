---
title: IMetaDataAssemblyEmit::DefineManifestResource-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48d688b64bbe9330a176ef073e96865b719ff2c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446680"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="c6c95-102">IMetaDataAssemblyEmit::DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="c6c95-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="c6c95-103">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="c6c95-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6c95-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6c95-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6c95-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c6c95-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="c6c95-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="c6c95-107">[in] Ein Metadatentoken des Typs `mdtFile` oder `mdtAssemblyRef` , der der Ressourcenanbieter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c6c95-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="c6c95-108">Ein NULL-Wert gibt an, dass die Datei, in der die Metadaten eingebettet ist, der Ressourcenanbieter ist.</span><span class="sxs-lookup"><span data-stu-id="c6c95-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="c6c95-109">[in] Der Offset auf den Anfang der Ressource in der Datei.</span><span class="sxs-lookup"><span data-stu-id="c6c95-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="c6c95-110">Für Ressourcen in eigenständigen Dateien wird dies immer 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c6c95-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="c6c95-111">Wenn die Ressource in einer PE (portable ausführbare) Datei eingebettet ist, ist dies ein Offset der Ressource-BLOB, das an die in der Headerdatei cor.h angegebenen Position beginnt.</span><span class="sxs-lookup"><span data-stu-id="c6c95-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="c6c95-112">[in] Eine bitweise Kombination der Flagwerte, die eigenschafteneinstellungen für die in der Ressourcendefinition angeben.</span><span class="sxs-lookup"><span data-stu-id="c6c95-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="c6c95-113">[out] Ein Zeiger auf die zurückgegebenen Metadaten-Token.</span><span class="sxs-lookup"><span data-stu-id="c6c95-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6c95-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6c95-114">Remarks</span></span>  
 <span data-ttu-id="c6c95-115">Eine `ManifestResource` Metadatenstruktur muss definiert werden, für jede Ressource, die in der Assembly aneinander gehängt Dateien implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c6c95-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c95-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6c95-116">Requirements</span></span>  
 <span data-ttu-id="c6c95-117">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6c95-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c95-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6c95-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6c95-119">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c6c95-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6c95-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c95-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c95-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6c95-121">See Also</span></span>  
 [<span data-ttu-id="c6c95-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6c95-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
