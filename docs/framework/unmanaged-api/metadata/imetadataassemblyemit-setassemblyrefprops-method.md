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
ms.openlocfilehash: 0a4f0fd100397fc52ca917c54f0276598d714640
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642843"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="f20ca-102">IMetaDataAssemblyEmit::SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="f20ca-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="f20ca-103">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="f20ca-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f20ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f20ca-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f20ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f20ca-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="f20ca-106">[in] Das Metadatentoken, der angibt, die `AssemblyRef` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f20ca-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="f20ca-107">[in] Der öffentliche Schlüssel des Herausgebers der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f20ca-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="f20ca-108">[in] Die Größe in Bytes der `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="f20ca-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="f20ca-109">[in] Der Benutzer lesbarer Textname der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f20ca-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="f20ca-110">[in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema-Informationen für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="f20ca-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f20ca-111">[in] Ein Zeiger auf den Hashwert der Daten zu dieser Assembly zugeordneten.</span><span class="sxs-lookup"><span data-stu-id="f20ca-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f20ca-112">[in] Die Größe in Bytes der `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="f20ca-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="f20ca-113">[in] Eine bitweise Kombination von [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) Werte, die Attribute der referenzierten Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="f20ca-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f20ca-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f20ca-114">Remarks</span></span>  
 <span data-ttu-id="f20ca-115">Zum Erstellen einer `AssemblyRef` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f20ca-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f20ca-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f20ca-116">Requirements</span></span>  
 <span data-ttu-id="f20ca-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f20ca-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f20ca-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f20ca-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f20ca-119">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f20ca-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f20ca-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f20ca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f20ca-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f20ca-121">See also</span></span>
- [<span data-ttu-id="f20ca-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f20ca-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
