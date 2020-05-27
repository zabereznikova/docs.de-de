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
ms.openlocfilehash: 9990daea1b097532de53684921d3f10c520a3b1a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008065"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="773ce-102">IMetaDataAssemblyEmit::SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="773ce-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="773ce-103">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="773ce-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="773ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="773ce-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="773ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="773ce-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="773ce-106">in Das Metadatentoken, das die `File` zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="773ce-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="773ce-107">in Ein Zeiger auf die Hashdaten, die der Datei zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="773ce-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="773ce-108">in Die Größe von in Bytes `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="773ce-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="773ce-109">in Eine bitweise Kombination von [CorFileFlags](corfileflags-enumeration.md) -Werten, die verschiedene Attribute der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="773ce-109">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="773ce-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="773ce-110">Remarks</span></span>  
 <span data-ttu-id="773ce-111">Verwenden Sie zum Erstellen einer `File` Metadatenstruktur die [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="773ce-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="773ce-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="773ce-112">Requirements</span></span>  
 <span data-ttu-id="773ce-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="773ce-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="773ce-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="773ce-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="773ce-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="773ce-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="773ce-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="773ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="773ce-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="773ce-117">See also</span></span>

- [<span data-ttu-id="773ce-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="773ce-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
