---
title: IMetaDataAssemblyEmit::SetFileProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f179ce3e54a5229423d7267cd52a97edef3b619d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="f0734-102">IMetaDataAssemblyEmit::SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="f0734-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="f0734-103">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="f0734-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0734-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0734-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0734-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0734-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="f0734-106">[in] Das Metadatentoken, der angibt, die `File` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0734-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f0734-107">[in] Ein Zeiger auf den Hashwert der Daten zu der Datei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f0734-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f0734-108">[in] Die Größe in Bytes des `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="f0734-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="f0734-109">[in] Eine bitweise Kombination von [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) Werte, die verschiedene Attribute der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="f0734-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0734-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0734-110">Remarks</span></span>  
 <span data-ttu-id="f0734-111">Zum Erstellen einer `File` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f0734-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0734-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0734-112">Requirements</span></span>  
 <span data-ttu-id="f0734-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0734-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0734-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f0734-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0734-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f0734-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f0734-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0734-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0734-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0734-117">See Also</span></span>  
 [<span data-ttu-id="f0734-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0734-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
