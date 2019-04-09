---
title: IMetaDataEmit::DefineUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f24dd3864be1bda454ac5e863f3fa2caf736bda9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215221"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="d202f-102">IMetaDataEmit::DefineUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="d202f-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="d202f-103">Ruft Metadaten für die angegebene Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="d202f-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d202f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d202f-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d202f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d202f-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="d202f-106">[in] Der zu speichernde Benutzerzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d202f-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="d202f-107">[in] Die Anzahl von Breitzeichen in `szString`.</span><span class="sxs-lookup"><span data-stu-id="d202f-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="d202f-108">[out] Das Zeichenfolgentoken, das zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d202f-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d202f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d202f-109">Requirements</span></span>  
 <span data-ttu-id="d202f-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d202f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d202f-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d202f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d202f-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d202f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d202f-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d202f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d202f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d202f-114">See also</span></span>

- [<span data-ttu-id="d202f-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d202f-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d202f-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d202f-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
