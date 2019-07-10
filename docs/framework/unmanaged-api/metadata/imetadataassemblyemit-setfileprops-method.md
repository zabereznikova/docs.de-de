---
title: IMetaDataAssemblyEmit::SetFileProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6505995b128e31ed2a18881d31afa0bb1bfe150e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779425"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="99515-102">IMetaDataAssemblyEmit::SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="99515-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="99515-103">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="99515-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99515-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99515-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99515-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99515-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="99515-106">[in] Das Metadatentoken, der angibt, die `File` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="99515-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="99515-107">[in] Ein Zeiger auf den Hashwert der Daten zu der Datei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="99515-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="99515-108">[in] Die Größe in Bytes der `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="99515-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="99515-109">[in] Eine bitweise Kombination von [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) Werte, die verschiedenen Attribute der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="99515-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99515-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99515-110">Remarks</span></span>  
 <span data-ttu-id="99515-111">Zum Erstellen einer `File` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="99515-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99515-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99515-112">Requirements</span></span>  
 <span data-ttu-id="99515-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99515-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99515-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="99515-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99515-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="99515-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99515-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99515-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99515-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99515-117">See also</span></span>

- [<span data-ttu-id="99515-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99515-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
