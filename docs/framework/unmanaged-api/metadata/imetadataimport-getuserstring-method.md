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
ms.openlocfilehash: 358ca84f32e1b233116605bf5486cc9a01b42e67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503502"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="5212a-102">IMetaDataImport::GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="5212a-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="5212a-103">Ruft das Zeichenfolgenliteral ab, das durch das angegebene Metadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5212a-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5212a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5212a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5212a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5212a-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="5212a-106">in Das Zeichen folgen Token, das die zugeordnete Zeichenfolge zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="5212a-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="5212a-107">vorgenommen Eine Kopie der angeforderten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5212a-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="5212a-108">in Die maximale Größe in breit Zeichen der angeforderten `szString` .</span><span class="sxs-lookup"><span data-stu-id="5212a-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="5212a-109">vorgenommen Die Größe der zurückgegebenen breit Zeichen `szString` .</span><span class="sxs-lookup"><span data-stu-id="5212a-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5212a-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5212a-110">Requirements</span></span>  
 <span data-ttu-id="5212a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5212a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5212a-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5212a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5212a-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5212a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5212a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5212a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5212a-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5212a-115">See also</span></span>

- [<span data-ttu-id="5212a-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5212a-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5212a-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5212a-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
