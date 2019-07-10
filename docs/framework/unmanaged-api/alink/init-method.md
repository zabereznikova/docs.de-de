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
ms.openlocfilehash: 606809533010f458272cd6fbbad6234217bddea2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741619"
---
# <a name="init-method"></a><span data-ttu-id="45578-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="45578-102">Init Method</span></span>
<span data-ttu-id="45578-103">Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="45578-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45578-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45578-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="45578-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45578-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="45578-106">[IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf den Metadatenverteiler.</span><span class="sxs-lookup"><span data-stu-id="45578-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="45578-107">[IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle die Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="45578-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45578-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45578-108">Return Value</span></span>  
 <span data-ttu-id="45578-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="45578-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45578-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45578-110">Requirements</span></span>  
 <span data-ttu-id="45578-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="45578-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45578-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45578-112">See also</span></span>

- [<span data-ttu-id="45578-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45578-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="45578-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45578-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="45578-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="45578-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
