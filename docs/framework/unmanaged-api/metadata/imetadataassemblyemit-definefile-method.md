---
title: IMetaDataAssemblyEmit::DefineFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineFile
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48584822d7a2f31c466401db3a24156a71ad7011
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="7f72e-102">IMetaDataAssemblyEmit::DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7f72e-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="7f72e-103">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="7f72e-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f72e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f72e-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f72e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f72e-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="7f72e-106">[in] Der Name der Datei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f72e-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7f72e-107">[in] Ein Zeiger auf den Hashwert der Daten zu der Assembly zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="7f72e-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7f72e-108">[in] Die Größe in Bytes des `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="7f72e-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="7f72e-109">[in] Eine bitweise Kombination von `FileFlags` Werte, die eigenschafteneinstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="7f72e-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="7f72e-110">[out] Ein Zeiger auf das zurückgegebene `File` token.</span><span class="sxs-lookup"><span data-stu-id="7f72e-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f72e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f72e-111">Remarks</span></span>  
 <span data-ttu-id="7f72e-112">Eine `File` Metadatenstruktur muss für jede Datei, die Bestandteil dieser Assembly zum Zeitpunkt, in denen diese Assembly erstellt wurde war, mit Ausnahme der Datei mit den Metadaten definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7f72e-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f72e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f72e-113">Requirements</span></span>  
 <span data-ttu-id="7f72e-114">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f72e-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f72e-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7f72e-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f72e-116">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7f72e-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f72e-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f72e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f72e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f72e-118">See Also</span></span>  
 [<span data-ttu-id="7f72e-119">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f72e-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
