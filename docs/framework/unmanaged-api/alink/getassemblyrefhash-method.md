---
title: GetAssemblyRefHash-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fa8d42f9e849db6a02f6c62b37e04cf5dee016e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119651"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="2af28-102">GetAssemblyRefHash-Methode</span><span class="sxs-lookup"><span data-stu-id="2af28-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="2af28-103">Ruft einen Hash-Blob für eine bestimmte Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="2af28-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2af28-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2af28-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2af28-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="2af28-106">ID der Assembly, der der Hash bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="2af28-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="2af28-107">Erhält die resultierende Hash-Blob.</span><span class="sxs-lookup"><span data-stu-id="2af28-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="2af28-108">Größe, wird der Hash-Blob in Bytes empfängt.</span><span class="sxs-lookup"><span data-stu-id="2af28-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2af28-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2af28-109">Return Value</span></span>  
 <span data-ttu-id="2af28-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2af28-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2af28-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2af28-111">Requirements</span></span>  
 <span data-ttu-id="2af28-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="2af28-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af28-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2af28-113">See also</span></span>

- [<span data-ttu-id="2af28-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2af28-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2af28-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2af28-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2af28-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2af28-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
