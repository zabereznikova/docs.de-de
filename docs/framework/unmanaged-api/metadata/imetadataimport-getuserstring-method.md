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
ms.openlocfilehash: 358346af540c8b6b7ee1523e763bebbacf8cd2bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127815"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="25967-102">IMetaDataImport::GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="25967-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="25967-103">Ruft das Zeichenfolgenliteral ab, das durch das angegebene Metadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="25967-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25967-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25967-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25967-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25967-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="25967-106">[in] Das Zeichenfolgentoken, das an die zugeordnete Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="25967-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="25967-107">[out] Eine Kopie der angeforderten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="25967-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="25967-108">[in] Die maximale Größe in Breitzeichen des angeforderten `szString`.</span><span class="sxs-lookup"><span data-stu-id="25967-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="25967-109">[out] Die Größe in Breitzeichen des zurückgegebenen `szString`.</span><span class="sxs-lookup"><span data-stu-id="25967-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25967-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25967-110">Requirements</span></span>  
 <span data-ttu-id="25967-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25967-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25967-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25967-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25967-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="25967-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="25967-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="25967-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25967-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25967-115">See also</span></span>

- [<span data-ttu-id="25967-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25967-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="25967-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25967-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
