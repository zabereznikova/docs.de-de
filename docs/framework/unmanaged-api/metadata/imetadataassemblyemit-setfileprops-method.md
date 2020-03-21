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
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176031"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="61a42-102">IMetaDataAssemblyEmit::SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="61a42-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="61a42-103">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="61a42-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61a42-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61a42-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61a42-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="61a42-106">[in] Das Metadatentoken, das `File` die zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="61a42-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="61a42-107">[in] Ein Zeiger auf die Hashdaten, die der Datei zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="61a42-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="61a42-108">[in] Die Größe in `pbHashValue`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="61a42-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="61a42-109">[in] Eine bitweise Kombination von [CorFileFlags-Werten,](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) die verschiedene Attribute der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="61a42-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61a42-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="61a42-110">Remarks</span></span>  
 <span data-ttu-id="61a42-111">Um eine `File` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::DefineFile-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)</span><span class="sxs-lookup"><span data-stu-id="61a42-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61a42-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="61a42-112">Requirements</span></span>  
 <span data-ttu-id="61a42-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61a42-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61a42-114">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61a42-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61a42-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="61a42-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61a42-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61a42-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a42-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61a42-117">See also</span></span>

- [<span data-ttu-id="61a42-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61a42-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
