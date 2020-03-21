---
title: IMetaDataAssemblyImport::EnumFiles-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 70f76318f51047cb81262f744a6fbed5fe401692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177818"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="66b8d-102">IMetaDataAssemblyImport::EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="66b8d-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="66b8d-103">Zählt die Dateien auf, auf die im aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="66b8d-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66b8d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66b8d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66b8d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66b8d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="66b8d-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="66b8d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="66b8d-107">Dies muss ein NULL-Wert für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="66b8d-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="66b8d-108">[out] Das Array, das `mdFile` zum Speichern der Metadatentoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66b8d-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="66b8d-109">[in] Die maximale `mdFile` Anzahl von Token, `rFiles`die in platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="66b8d-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="66b8d-110">[out] Die Anzahl `mdFile` der Token, `rFiles`die tatsächlich in platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="66b8d-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66b8d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="66b8d-111">Return Value</span></span>  
  
|<span data-ttu-id="66b8d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66b8d-112">HRESULT</span></span>|<span data-ttu-id="66b8d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66b8d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="66b8d-114">`EnumFiles`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="66b8d-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="66b8d-115">Es sind keine Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="66b8d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="66b8d-116">In diesem `pcTokens` Fall ist auf Null gesetzt.</span><span class="sxs-lookup"><span data-stu-id="66b8d-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66b8d-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="66b8d-117">Requirements</span></span>  
 <span data-ttu-id="66b8d-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66b8d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66b8d-119">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66b8d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66b8d-120">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="66b8d-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66b8d-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66b8d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b8d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66b8d-122">See also</span></span>

- [<span data-ttu-id="66b8d-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66b8d-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
