---
title: GetAssemblyRefHash-Methode
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
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99ae38025f223d669a428738783676ebc0687554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="6e865-102">GetAssemblyRefHash-Methode</span><span class="sxs-lookup"><span data-stu-id="6e865-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="6e865-103">Ruft ein Hash-Blob für eine bestimmte Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="6e865-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e865-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e865-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e865-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e865-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="6e865-106">ID der Assembly, auf die der Hashwert verweisen wird.</span><span class="sxs-lookup"><span data-stu-id="6e865-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="6e865-107">Erhält die resultierende Hash-Blob.</span><span class="sxs-lookup"><span data-stu-id="6e865-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="6e865-108">Größe, wird der Hash-Blob in Bytes empfängt.</span><span class="sxs-lookup"><span data-stu-id="6e865-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e865-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e865-109">Return Value</span></span>  
 <span data-ttu-id="6e865-110">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e865-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e865-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e865-111">Requirements</span></span>  
 <span data-ttu-id="6e865-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="6e865-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e865-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e865-113">See Also</span></span>  
 [<span data-ttu-id="6e865-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e865-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="6e865-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e865-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="6e865-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="6e865-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
