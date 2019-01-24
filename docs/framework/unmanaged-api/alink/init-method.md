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
ms.openlocfilehash: 315ddf89d9c0653f357490dc31986dc302024622
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662646"
---
# <a name="init-method"></a><span data-ttu-id="c6870-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="c6870-102">Init Method</span></span>
<span data-ttu-id="c6870-103">Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c6870-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6870-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6870-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6870-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6870-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="c6870-106">[IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf den Metadatenverteiler.</span><span class="sxs-lookup"><span data-stu-id="c6870-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="c6870-107">[IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle die Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="c6870-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6870-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c6870-108">Return Value</span></span>  
 <span data-ttu-id="c6870-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c6870-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6870-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6870-110">Requirements</span></span>  
 <span data-ttu-id="c6870-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="c6870-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6870-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6870-112">See also</span></span>
- [<span data-ttu-id="c6870-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6870-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c6870-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6870-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c6870-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c6870-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
