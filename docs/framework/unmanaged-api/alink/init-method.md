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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119365"
---
# <a name="init-method"></a><span data-ttu-id="a3f01-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="a3f01-102">Init Method</span></span>
<span data-ttu-id="a3f01-103">Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="a3f01-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3f01-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3f01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3f01-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="a3f01-106">[IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf den Metadatenverteiler.</span><span class="sxs-lookup"><span data-stu-id="a3f01-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="a3f01-107">[IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle die Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="a3f01-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3f01-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3f01-108">Return Value</span></span>  
 <span data-ttu-id="a3f01-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a3f01-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f01-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3f01-110">Requirements</span></span>  
 <span data-ttu-id="a3f01-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="a3f01-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f01-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3f01-112">See also</span></span>

- [<span data-ttu-id="a3f01-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3f01-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a3f01-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3f01-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a3f01-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a3f01-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
