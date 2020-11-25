---
title: IMetaDataImport::GetSigFromToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
ms.openlocfilehash: 67abdfd8f8c67299eae757533f20df69392f25b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729186"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="f57ba-102">IMetaDataImport::GetSigFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f57ba-102">IMetaDataImport::GetSigFromToken Method</span></span>

<span data-ttu-id="f57ba-103">Ruft die binäre Metadatensignatur ab, die dem angegebenen Token zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f57ba-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f57ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f57ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f57ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f57ba-105">Parameters</span></span>  

 `mdSig`  
 <span data-ttu-id="f57ba-106">in Das Token, für das die binäre Metadatensignatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="f57ba-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="f57ba-107">vorgenommen Ein Zeiger auf die zurückgegebene Metadatensignatur.</span><span class="sxs-lookup"><span data-stu-id="f57ba-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="f57ba-108">vorgenommen Die Größe der binären Metadatensignatur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f57ba-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f57ba-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f57ba-109">Requirements</span></span>  

 <span data-ttu-id="f57ba-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f57ba-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f57ba-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f57ba-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f57ba-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f57ba-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f57ba-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f57ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57ba-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f57ba-114">See also</span></span>

- [<span data-ttu-id="f57ba-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f57ba-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f57ba-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f57ba-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
