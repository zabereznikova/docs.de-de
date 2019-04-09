---
title: IMetaDataAssemblyImport::EnumExportedTypes-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c32dcfe5d00e1d35f7c63aa98a33d26f6b179c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152684"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="223b9-102">IMetaDataAssemblyImport::EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="223b9-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="223b9-103">Listet die exportierten Typen in das Assemblymanifest im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="223b9-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="223b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="223b9-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="223b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="223b9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="223b9-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="223b9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="223b9-107">Dies muss ein NULL-Wert sein Wert fest, wenn die `EnumExportedTypes` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="223b9-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="223b9-108">[out] Die Enumeration von `mdExportedType` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="223b9-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="223b9-109">[in] Die maximale Anzahl von `mdExportedType` Token, die in platziert werden, können die `rExportedTypes` Array.</span><span class="sxs-lookup"><span data-stu-id="223b9-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="223b9-110">[out] Die Anzahl der `mdExportedType` Token, die tatsächlich in `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="223b9-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="223b9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="223b9-111">Return Value</span></span>  
  
|<span data-ttu-id="223b9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="223b9-112">HRESULT</span></span>|<span data-ttu-id="223b9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="223b9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes` <span data-ttu-id="223b9-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="223b9-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="223b9-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="223b9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="223b9-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="223b9-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="223b9-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="223b9-117">Requirements</span></span>  
 <span data-ttu-id="223b9-118">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="223b9-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="223b9-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="223b9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="223b9-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="223b9-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="223b9-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="223b9-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="223b9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="223b9-122">See also</span></span>

- [<span data-ttu-id="223b9-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="223b9-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
