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
ms.openlocfilehash: fb381a872cbeb787da0c6920f2cdeef434fb33ea
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008091"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="3e210-102">IMetaDataAssemblyEmit::SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="3e210-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="3e210-103">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="3e210-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e210-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e210-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3e210-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3e210-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="3e210-106">in Das Metadatentoken, das die `AssemblyRef` zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="3e210-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="3e210-107">in Der öffentliche Schlüssel des Verlegers der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3e210-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="3e210-108">in Die Größe von in Bytes `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="3e210-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="3e210-109">in Der lesbare Textname der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3e210-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="3e210-110">in Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Versions-, Platt Form-und Gebiets Schema Informationen für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="3e210-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="3e210-111">in Ein Zeiger auf die Hashdaten, die der Assembly zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3e210-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="3e210-112">in Die Größe von in Bytes `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="3e210-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="3e210-113">in Eine bitweise Kombination von [AssemblyRefFlags](assemblyrefflags-enumeration.md) -Werten, die Attribute der Assembly angeben, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3e210-113">[in] A bitwise combination of [AssemblyRefFlags](assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e210-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e210-114">Remarks</span></span>  
 <span data-ttu-id="3e210-115">Verwenden Sie zum Erstellen einer `AssemblyRef` Metadatenstruktur die [IMetaDataAssemblyEmit::D efineassemblyref](imetadataassemblyemit-defineassemblyref-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="3e210-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e210-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3e210-116">Requirements</span></span>  
 <span data-ttu-id="3e210-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e210-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e210-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3e210-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e210-119">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e210-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e210-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e210-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e210-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e210-121">See also</span></span>

- [<span data-ttu-id="3e210-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3e210-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
