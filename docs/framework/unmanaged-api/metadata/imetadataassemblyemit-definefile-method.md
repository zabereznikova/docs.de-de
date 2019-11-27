---
title: IMetaDataAssemblyEmit::DefineFile-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: 0b7ca6f9878ed2fa2d90ea93e5101f0a66ec2d5e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440210"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="e8db4-102">IMetaDataAssemblyEmit::DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="e8db4-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="e8db4-103">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="e8db4-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8db4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8db4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8db4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8db4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e8db4-106">in Der Name der zu verwendenden Datei.</span><span class="sxs-lookup"><span data-stu-id="e8db4-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="e8db4-107">in Ein Zeiger auf die Hashdaten, die der Assembly zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8db4-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="e8db4-108">in Die Größe `pbHashValue`in Byte.</span><span class="sxs-lookup"><span data-stu-id="e8db4-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="e8db4-109">in Eine bitweise Kombination von `FileFlags`-Werten, die Eigenschafts Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="e8db4-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="e8db4-110">vorgenommen Ein Zeiger auf das zurückgegebene `File` Token.</span><span class="sxs-lookup"><span data-stu-id="e8db4-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8db4-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8db4-111">Remarks</span></span>  
 <span data-ttu-id="e8db4-112">Für jede Datei, die zum Zeitpunkt der Erstellung dieser Assembly Bestandteil dieser Assembly war, muss eine `File` Metadatenstruktur definiert werden, ausgenommen die Datei, die die Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="e8db4-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8db4-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e8db4-113">Requirements</span></span>  
 <span data-ttu-id="e8db4-114">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8db4-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8db4-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e8db4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8db4-116">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8db4-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8db4-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8db4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8db4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8db4-118">See also</span></span>

- [<span data-ttu-id="e8db4-119">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8db4-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
