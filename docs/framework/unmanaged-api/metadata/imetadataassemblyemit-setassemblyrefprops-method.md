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
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176044"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="65561-102">IMetaDataAssemblyEmit::SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="65561-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="65561-103">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="65561-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65561-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65561-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="65561-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65561-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="65561-106">[in] Das Metadatentoken, das `AssemblyRef` die zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="65561-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="65561-107">[in] Der öffentliche Schlüssel des Herausgebers der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="65561-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="65561-108">[in] Die Größe in `pbPublicKeyOrToken`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="65561-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="65561-109">[in] Der vom Menschen lesbare Textname der Assembly.</span><span class="sxs-lookup"><span data-stu-id="65561-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="65561-110">[in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Versions-, Plattform- und Gebietsschemainformationen für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="65561-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="65561-111">[in] Ein Zeiger auf die Hashdaten, die der Assembly zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="65561-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="65561-112">[in] Die Größe in `pbHashValue`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="65561-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="65561-113">[in] Eine bitweise Kombination von [AssemblyRefFlags-Werten,](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) die Attribute der assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="65561-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65561-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="65561-114">Remarks</span></span>  
 <span data-ttu-id="65561-115">Um eine `AssemblyRef` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::DefineAssemblyRef-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)</span><span class="sxs-lookup"><span data-stu-id="65561-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65561-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="65561-116">Requirements</span></span>  
 <span data-ttu-id="65561-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65561-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65561-118">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="65561-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65561-119">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="65561-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65561-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65561-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65561-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65561-121">See also</span></span>

- [<span data-ttu-id="65561-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65561-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
