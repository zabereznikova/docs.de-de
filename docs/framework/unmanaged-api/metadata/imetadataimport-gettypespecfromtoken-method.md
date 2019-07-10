---
title: IMetaDataImport::GetTypeSpecFromToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7e060d2f72609b470dbd5060746a1458f5eed9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782309"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="17af1-102">IMetaDataImport::GetTypeSpecFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="17af1-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="17af1-103">Ruft die binäre Metadatensignatur der Typspezifikation ab, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="17af1-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17af1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17af1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17af1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17af1-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="17af1-106">[in] Das TypeSpec-Token, das die Signatur für die angeforderten Metadaten zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="17af1-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="17af1-107">[out] Ein Zeiger auf die binäre Metadatensignatur.</span><span class="sxs-lookup"><span data-stu-id="17af1-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="17af1-108">[out] Die Größe in Byte der Signatur der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="17af1-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17af1-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17af1-109">Return Value</span></span>  
 <span data-ttu-id="17af1-110">Ein HRESULT, der Erfolg oder Misserfolg angibt.</span><span class="sxs-lookup"><span data-stu-id="17af1-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="17af1-111">Fehler können mit dem Makro FAILED getestet werden.</span><span class="sxs-lookup"><span data-stu-id="17af1-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17af1-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17af1-112">Requirements</span></span>  
 <span data-ttu-id="17af1-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17af1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17af1-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="17af1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17af1-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="17af1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17af1-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17af1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17af1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17af1-117">See also</span></span>

- [<span data-ttu-id="17af1-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17af1-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="17af1-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17af1-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
