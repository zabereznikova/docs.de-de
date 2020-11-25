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
ms.openlocfilehash: 9cf5f3d926c1e742dd9134e7bf292df53e1a4909
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720177"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="e9c62-102">IMetaDataAssemblyEmit::SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e9c62-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>

<span data-ttu-id="e9c62-103">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="e9c62-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9c62-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c62-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9c62-105">Parameters</span></span>  

 `file`  
 <span data-ttu-id="e9c62-106">in Das Metadatentoken, das die `File` zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="e9c62-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="e9c62-107">in Ein Zeiger auf die Hashdaten, die der Datei zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e9c62-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="e9c62-108">in Die Größe von in Bytes `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="e9c62-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="e9c62-109">in Eine bitweise Kombination von [CorFileFlags](corfileflags-enumeration.md) -Werten, die verschiedene Attribute der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="e9c62-109">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9c62-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9c62-110">Remarks</span></span>  

 <span data-ttu-id="e9c62-111">Verwenden Sie zum Erstellen einer `File` Metadatenstruktur die [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="e9c62-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9c62-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e9c62-112">Requirements</span></span>  

 <span data-ttu-id="e9c62-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9c62-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c62-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9c62-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9c62-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9c62-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9c62-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c62-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c62-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9c62-117">See also</span></span>

- [<span data-ttu-id="e9c62-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9c62-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
