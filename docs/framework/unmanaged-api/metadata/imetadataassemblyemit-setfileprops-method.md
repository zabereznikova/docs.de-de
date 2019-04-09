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
ms.openlocfilehash: fd0c2da234fa89bbf92c2117d6428d64502da0c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208175"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="e547c-102">IMetaDataAssemblyEmit::SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e547c-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="e547c-103">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="e547c-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e547c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e547c-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e547c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e547c-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="e547c-106">[in] Das Metadatentoken, der angibt, die `File` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e547c-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="e547c-107">[in] Ein Zeiger auf den Hashwert der Daten zu der Datei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e547c-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="e547c-108">[in] Die Größe in Bytes der `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="e547c-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="e547c-109">[in] Eine bitweise Kombination von [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) Werte, die verschiedenen Attribute der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="e547c-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e547c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e547c-110">Remarks</span></span>  
 <span data-ttu-id="e547c-111">Zum Erstellen einer `File` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e547c-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e547c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e547c-112">Requirements</span></span>  
 <span data-ttu-id="e547c-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e547c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e547c-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e547c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e547c-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e547c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e547c-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e547c-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e547c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e547c-117">See also</span></span>

- [<span data-ttu-id="e547c-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e547c-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
