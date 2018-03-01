---
title: EnumImportTypes-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 08644816d3fa11ade5a8ebee1573e8f66d526101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="e092d-102">EnumImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="e092d-102">EnumImportTypes Method</span></span>
<span data-ttu-id="e092d-103">Listet jeden Typ in jedem Bereich.</span><span class="sxs-lookup"><span data-stu-id="e092d-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e092d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e092d-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e092d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e092d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e092d-106">Handle für Enumerator.</span><span class="sxs-lookup"><span data-stu-id="e092d-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="e092d-107">Maximale Anzahl von Typen, die abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e092d-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="e092d-108">Empfängt Typtoken, nicht zu überschreiten `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="e092d-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="e092d-109">Empfängt die tatsächliche Anzahl des Typs im `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="e092d-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e092d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e092d-110">Return Value</span></span>  
 <span data-ttu-id="e092d-111">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e092d-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e092d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e092d-112">Requirements</span></span>  
 <span data-ttu-id="e092d-113">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="e092d-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e092d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e092d-114">See Also</span></span>  
 [<span data-ttu-id="e092d-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e092d-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e092d-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e092d-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e092d-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="e092d-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
