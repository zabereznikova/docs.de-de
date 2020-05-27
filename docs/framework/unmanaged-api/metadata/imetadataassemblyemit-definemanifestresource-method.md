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
ms.openlocfilehash: 026f5efe195cdb34999b65c5f47de6f68d30e11a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008130"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="52f3a-102">IMetaDataAssemblyEmit::DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="52f3a-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="52f3a-103">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="52f3a-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52f3a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52f3a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="52f3a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="52f3a-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="52f3a-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="52f3a-107">in Ein Metadatentoken vom Typ `mdtFile` oder `mdtAssemblyRef` , das dem Ressourcenanbieter zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="52f3a-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="52f3a-108">Ein NULL-Wert gibt an, dass die Datei, in die die Metadaten eingebettet sind, der Ressourcenanbieter ist.</span><span class="sxs-lookup"><span data-stu-id="52f3a-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="52f3a-109">in Der Offset zum Anfang der Ressource innerhalb der Datei.</span><span class="sxs-lookup"><span data-stu-id="52f3a-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="52f3a-110">Für Ressourcen in eigenständigen Dateien ist dies immer 0 (null).</span><span class="sxs-lookup"><span data-stu-id="52f3a-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="52f3a-111">Wenn die Ressource in eine ausführbare PE-Datei (portable ausführbare Datei) eingebettet ist, handelt es sich hierbei um einen Offset des ressourcenblobs, der an dem in der "Cor. h"-Header Datei angegebenen Speicherort beginnt.</span><span class="sxs-lookup"><span data-stu-id="52f3a-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="52f3a-112">in Eine bitweise Kombination von Flagwerten, die Eigenschafts Einstellungen für die Ressourcendefinition angeben.</span><span class="sxs-lookup"><span data-stu-id="52f3a-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="52f3a-113">vorgenommen Ein Zeiger auf das zurückgegebene Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="52f3a-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52f3a-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52f3a-114">Remarks</span></span>  
 <span data-ttu-id="52f3a-115">Eine `ManifestResource` Metadatenstruktur muss für jede Ressource definiert werden, die in jeder der Assemblydateien implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="52f3a-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52f3a-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="52f3a-116">Requirements</span></span>  
 <span data-ttu-id="52f3a-117">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52f3a-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52f3a-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="52f3a-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52f3a-119">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="52f3a-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52f3a-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52f3a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f3a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52f3a-121">See also</span></span>

- [<span data-ttu-id="52f3a-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52f3a-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
