---
title: Init-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.Init
api_location: alink.dll
api_type: COM
f1_keywords: Init
helpviewer_keywords: Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 999f572d27f75094ecc72c59acee7d35f86d5342
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="init-method"></a><span data-ttu-id="8eef5-102">Init-Methode</span><span class="sxs-lookup"><span data-stu-id="8eef5-102">Init Method</span></span>
<span data-ttu-id="8eef5-103">Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="8eef5-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eef5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8eef5-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8eef5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8eef5-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="8eef5-106">[IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf die Metadatenverteiler.</span><span class="sxs-lookup"><span data-stu-id="8eef5-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="8eef5-107">[IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle der Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="8eef5-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8eef5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8eef5-108">Return Value</span></span>  
 <span data-ttu-id="8eef5-109">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8eef5-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eef5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8eef5-110">Requirements</span></span>  
 <span data-ttu-id="8eef5-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="8eef5-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eef5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8eef5-112">See Also</span></span>  
 [<span data-ttu-id="8eef5-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eef5-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8eef5-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eef5-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8eef5-115">ALink-API</span><span class="sxs-lookup"><span data-stu-id="8eef5-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
