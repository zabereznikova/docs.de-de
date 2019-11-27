---
title: IMetaDataImport::IsValidToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: edf24de8ae38aab97e41a53cc86ae5aa6c592c50
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434693"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="f4150-102">IMetaDataImport::IsValidToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f4150-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="f4150-103">Ruft einen Wert ab, der angibt, ob das angegebene Token einen gültigen Verweis auf ein Codeobjekt enthält.</span><span class="sxs-lookup"><span data-stu-id="f4150-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4150-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4150-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4150-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f4150-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f4150-106">in Das Token, für das die Verweis Gültigkeit überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4150-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4150-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f4150-107">Return Value</span></span>  
 <span data-ttu-id="f4150-108">`true`, wenn `tk` ein gültiges Metadatentoken im aktuellen Bereich ist.</span><span class="sxs-lookup"><span data-stu-id="f4150-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="f4150-109">Andernfalls ist der Wert `false`.</span><span class="sxs-lookup"><span data-stu-id="f4150-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4150-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f4150-110">Requirements</span></span>  
 <span data-ttu-id="f4150-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4150-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4150-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4150-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4150-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f4150-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4150-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4150-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4150-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4150-115">See also</span></span>

- [<span data-ttu-id="f4150-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4150-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f4150-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4150-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
