---
title: Init-Methode
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60602462376543fe934bb3c58bc4988fa8ab34bf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119365"
---
# <a name="init-method"></a><span data-ttu-id="d9fa3-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="d9fa3-102">Init Method</span></span>
<span data-ttu-id="d9fa3-103">Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d9fa3-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fa3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9fa3-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9fa3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9fa3-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="d9fa3-106">[IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf den Metadatenverteiler.</span><span class="sxs-lookup"><span data-stu-id="d9fa3-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="d9fa3-107">[IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle die Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="d9fa3-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9fa3-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d9fa3-108">Return Value</span></span>  
 <span data-ttu-id="d9fa3-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d9fa3-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9fa3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9fa3-110">Requirements</span></span>  
 <span data-ttu-id="d9fa3-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="d9fa3-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fa3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9fa3-112">See also</span></span>

- [<span data-ttu-id="d9fa3-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9fa3-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d9fa3-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9fa3-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d9fa3-115">ALink-API</span><span class="sxs-lookup"><span data-stu-id="d9fa3-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
