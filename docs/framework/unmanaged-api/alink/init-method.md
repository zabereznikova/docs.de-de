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
ms.openlocfilehash: bf96770dd58c9b84596c082a615f626ec723cc6c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787248"
---
# <a name="init-method"></a><span data-ttu-id="fa933-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="fa933-102">Init Method</span></span>
<span data-ttu-id="fa933-103">Bereitet Objekte vor, die die [IALink-Schnittstelle](ialink-interface.md) zur Verwendung implementieren.</span><span class="sxs-lookup"><span data-stu-id="fa933-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa933-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa933-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa933-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa933-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="fa933-106">[IMetaDataDispenserEx-Schnittstellen](../metadata/imetadatadispenserex-interface.md) Zeiger auf den metadatendispenser.</span><span class="sxs-lookup"><span data-stu-id="fa933-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="fa933-107">[IMetaDataError-Schnittstellen](../metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle zur Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="fa933-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa933-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa933-108">Return Value</span></span>  
 <span data-ttu-id="fa933-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="fa933-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa933-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa933-110">Requirements</span></span>  
 <span data-ttu-id="fa933-111">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="fa933-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa933-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa933-112">See also</span></span>

- [<span data-ttu-id="fa933-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa933-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fa933-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa933-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fa933-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="fa933-115">ALink API</span></span>](index.md)
