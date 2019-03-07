---
title: IMetaDataImport::GetUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d610385cfbfcb6a625e0e1893f97525f6f5430c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500602"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="15294-102">IMetaDataImport::GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="15294-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="15294-103">Ruft das Zeichenfolgenliteral ab, das durch das angegebene Metadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="15294-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15294-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15294-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15294-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15294-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="15294-106">[in] Das Zeichenfolgentoken, das an die zugeordnete Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="15294-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="15294-107">[out] Eine Kopie der angeforderten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="15294-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="15294-108">[in] Die maximale Größe in Breitzeichen des angeforderten `szString`.</span><span class="sxs-lookup"><span data-stu-id="15294-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="15294-109">[out] Die Größe in Breitzeichen des zurückgegebenen `szString`.</span><span class="sxs-lookup"><span data-stu-id="15294-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15294-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15294-110">Requirements</span></span>  
 <span data-ttu-id="15294-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15294-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15294-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15294-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15294-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15294-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15294-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15294-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15294-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15294-115">See also</span></span>
- [<span data-ttu-id="15294-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15294-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="15294-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15294-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
