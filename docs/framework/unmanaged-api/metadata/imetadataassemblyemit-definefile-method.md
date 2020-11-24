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
ms.openlocfilehash: 1dd71dbe0ddb894cb5ed05c32e50429d27c66aa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689328"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="64b23-102">IMetaDataAssemblyEmit::DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="64b23-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>

<span data-ttu-id="64b23-103">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="64b23-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64b23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64b23-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64b23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="64b23-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="64b23-106">in Der Name der zu verwendenden Datei.</span><span class="sxs-lookup"><span data-stu-id="64b23-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="64b23-107">in Ein Zeiger auf die Hashdaten, die der Assembly zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="64b23-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="64b23-108">in Die Größe von in Bytes `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="64b23-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="64b23-109">in Eine bitweise Kombination von- `FileFlags` Werten, die Eigenschafts Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="64b23-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="64b23-110">vorgenommen Ein Zeiger auf das zurückgegebene `File` Token.</span><span class="sxs-lookup"><span data-stu-id="64b23-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64b23-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64b23-111">Remarks</span></span>  

 <span data-ttu-id="64b23-112">Für jede Datei, die zum Zeitpunkt der Erstellung `File` dieser Assembly Bestandteil dieser Assembly war, muss eine Metadatenstruktur definiert werden, ausgenommen die Datei, die die Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="64b23-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64b23-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="64b23-113">Requirements</span></span>  

 <span data-ttu-id="64b23-114">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64b23-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64b23-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="64b23-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64b23-116">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="64b23-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64b23-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64b23-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b23-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64b23-118">See also</span></span>

- [<span data-ttu-id="64b23-119">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64b23-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
