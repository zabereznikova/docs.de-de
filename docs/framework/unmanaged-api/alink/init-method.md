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
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726017"
---
# <a name="init-method"></a><span data-ttu-id="e46bb-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="e46bb-102">Init Method</span></span>

<span data-ttu-id="e46bb-103">Bereitet Objekte vor, die die [IALink-Schnittstelle](ialink-interface.md) zur Verwendung implementieren.</span><span class="sxs-lookup"><span data-stu-id="e46bb-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e46bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e46bb-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e46bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e46bb-105">Parameters</span></span>  

 `pDispenser`  
 <span data-ttu-id="e46bb-106">[IMetaDataDispenserEx-Schnittstellen](../metadata/imetadatadispenserex-interface.md) Zeiger auf den metadatendispenser.</span><span class="sxs-lookup"><span data-stu-id="e46bb-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="e46bb-107">[IMetaDataError-Schnittstellen](../metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle zur Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="e46bb-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e46bb-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e46bb-108">Return Value</span></span>  

 <span data-ttu-id="e46bb-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="e46bb-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e46bb-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e46bb-110">Requirements</span></span>  

 <span data-ttu-id="e46bb-111">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="e46bb-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e46bb-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e46bb-112">See also</span></span>

- [<span data-ttu-id="e46bb-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e46bb-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e46bb-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e46bb-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e46bb-115">ALink-API</span><span class="sxs-lookup"><span data-stu-id="e46bb-115">ALink API</span></span>](index.md)
