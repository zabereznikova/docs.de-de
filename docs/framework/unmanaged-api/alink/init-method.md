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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949109"
---
# <a name="init-method"></a><span data-ttu-id="01e52-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="01e52-102">Init Method</span></span>
<span data-ttu-id="01e52-103">Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="01e52-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01e52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01e52-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="01e52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01e52-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="01e52-106">[IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf den Metadatenverteiler.</span><span class="sxs-lookup"><span data-stu-id="01e52-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="01e52-107">[IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle die Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="01e52-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01e52-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="01e52-108">Return Value</span></span>  
 <span data-ttu-id="01e52-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="01e52-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01e52-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01e52-110">Requirements</span></span>  
 <span data-ttu-id="01e52-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="01e52-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e52-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01e52-112">See also</span></span>

- [<span data-ttu-id="01e52-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01e52-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="01e52-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01e52-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="01e52-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="01e52-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
