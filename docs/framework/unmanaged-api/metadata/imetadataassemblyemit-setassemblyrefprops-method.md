---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6667812ab7f9acff2a66e458f68d77a0d670bc2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446906"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="1d751-102">IMetaDataAssemblyEmit::SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="1d751-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="1d751-103">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="1d751-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d751-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d751-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d751-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d751-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="1d751-106">[in] Das Metadatentoken, der angibt, die `AssemblyRef` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1d751-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="1d751-107">[in] Der öffentliche Schlüssel des Herausgebers der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1d751-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="1d751-108">[in] Die Größe in Bytes des `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="1d751-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="1d751-109">[in] Der lesbare Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="1d751-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="1d751-110">[in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="1d751-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="1d751-111">[in] Ein Zeiger auf den Hashwert der Daten zu der Assembly zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1d751-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="1d751-112">[in] Die Größe in Bytes des `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="1d751-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="1d751-113">[in] Eine bitweise Kombination von [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) Werte, die Attribute der referenzierten Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="1d751-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d751-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d751-114">Remarks</span></span>  
 <span data-ttu-id="1d751-115">Zum Erstellen einer `AssemblyRef` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="1d751-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d751-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d751-116">Requirements</span></span>  
 <span data-ttu-id="1d751-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d751-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d751-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d751-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d751-119">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="1d751-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d751-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d751-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d751-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d751-121">See Also</span></span>  
 [<span data-ttu-id="1d751-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d751-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
