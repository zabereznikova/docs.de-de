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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6dac6bb6790876e28f1a5cd72f0635a1155caa47
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481039"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="79a39-102">IMetaDataAssemblyEmit::DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="79a39-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="79a39-103">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="79a39-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79a39-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79a39-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="79a39-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="79a39-106">[in] Der Name der Datei, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79a39-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="79a39-107">[in] Ein Zeiger auf den Hashwert der Daten zu dieser Assembly zugeordneten.</span><span class="sxs-lookup"><span data-stu-id="79a39-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="79a39-108">[in] Die Größe in Bytes der `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="79a39-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="79a39-109">[in] Eine bitweise Kombination von `FileFlags` Werte, die eigenschafteneinstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="79a39-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="79a39-110">[out] Ein Zeiger auf das zurückgegebene `File` token.</span><span class="sxs-lookup"><span data-stu-id="79a39-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a39-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79a39-111">Remarks</span></span>  
 <span data-ttu-id="79a39-112">Eine `File` muss für jede Datei, die Bestandteil dieser Assembly zum Zeitpunkt, die diese Assembly erstellt wurde war, mit Ausnahme der Datei, die die Metadaten enthält, definiert werden.</span><span class="sxs-lookup"><span data-stu-id="79a39-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79a39-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79a39-113">Requirements</span></span>  
 <span data-ttu-id="79a39-114">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79a39-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a39-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="79a39-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79a39-116">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="79a39-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79a39-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79a39-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a39-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79a39-118">See also</span></span>
- [<span data-ttu-id="79a39-119">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79a39-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
