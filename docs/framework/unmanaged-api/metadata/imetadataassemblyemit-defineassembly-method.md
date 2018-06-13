---
title: IMetaDataAssemblyEmit::DefineAssembly-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9115657c52f31d9b7b7da3c843338670343da26c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446472"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="5b1a9-102">IMetaDataAssemblyEmit::DefineAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="5b1a9-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="5b1a9-103">Erstellt eine `Assembly` Struktur, die Metadaten für die angegebene Assembly und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b1a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b1a9-104">Syntax</span></span>  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b1a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b1a9-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="5b1a9-106">[in] Der öffentliche Schlüssel, der den Herausgeber der Assembly oder NULL angibt, wenn die Assembly keinen starken Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="5b1a9-107">[in] Die Größe in Bytes des `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="5b1a9-108">[in] Der Bezeichner des Hashalgorithmus für die Verschlüsselung von Dateien in der Assembly oder NULL, wenn der SHA-1-Algorithmus angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="5b1a9-109">[in] Der lesbare Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="5b1a9-110">Dieser Wert darf 1024 Zeichen nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5b1a9-111">[in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="5b1a9-112">[in] Eine Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte, die Funktionen der Assembly zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="5b1a9-113">[out] Ein Zeiger auf das Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b1a9-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b1a9-114">Remarks</span></span>  
 <span data-ttu-id="5b1a9-115">Nur ein `Assembly` Metadatenstruktur innerhalb eines Manifests definiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5b1a9-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b1a9-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b1a9-116">Requirements</span></span>  
 <span data-ttu-id="5b1a9-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b1a9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b1a9-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b1a9-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b1a9-119">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5b1a9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b1a9-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b1a9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b1a9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b1a9-121">See Also</span></span>  
 [<span data-ttu-id="5b1a9-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b1a9-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
