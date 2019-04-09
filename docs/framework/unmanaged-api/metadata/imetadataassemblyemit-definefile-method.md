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
ms.openlocfilehash: 5693da3b5e6d883efd9ad8a5a409a5dba8dd8b6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203430"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="7c4cf-102">IMetaDataAssemblyEmit::DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7c4cf-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="7c4cf-103">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="7c4cf-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c4cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c4cf-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c4cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c4cf-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="7c4cf-106">[in] Der Name der Datei, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c4cf-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7c4cf-107">[in] Ein Zeiger auf den Hashwert der Daten zu dieser Assembly zugeordneten.</span><span class="sxs-lookup"><span data-stu-id="7c4cf-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7c4cf-108">[in] Die Größe in Bytes der `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="7c4cf-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="7c4cf-109">[in] Eine bitweise Kombination von `FileFlags` Werte, die eigenschafteneinstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="7c4cf-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="7c4cf-110">[out] Ein Zeiger auf das zurückgegebene `File` token.</span><span class="sxs-lookup"><span data-stu-id="7c4cf-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c4cf-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c4cf-111">Remarks</span></span>  
 <span data-ttu-id="7c4cf-112">Eine `File` muss für jede Datei, die Bestandteil dieser Assembly zum Zeitpunkt, die diese Assembly erstellt wurde war, mit Ausnahme der Datei, die die Metadaten enthält, definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7c4cf-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c4cf-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c4cf-113">Requirements</span></span>  
 <span data-ttu-id="7c4cf-114">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c4cf-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c4cf-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c4cf-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c4cf-116">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7c4cf-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7c4cf-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7c4cf-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c4cf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c4cf-118">See also</span></span>

- [<span data-ttu-id="7c4cf-119">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c4cf-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
