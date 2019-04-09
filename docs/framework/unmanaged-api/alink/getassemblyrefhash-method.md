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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119651"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="b4208-102">GetAssemblyRefHash-Methode</span><span class="sxs-lookup"><span data-stu-id="b4208-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="b4208-103">Ruft einen Hash-Blob für eine bestimmte Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="b4208-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4208-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4208-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4208-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4208-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="b4208-106">ID der Assembly, der der Hash bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b4208-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="b4208-107">Erhält die resultierende Hash-Blob.</span><span class="sxs-lookup"><span data-stu-id="b4208-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="b4208-108">Größe, wird der Hash-Blob in Bytes empfängt.</span><span class="sxs-lookup"><span data-stu-id="b4208-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4208-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4208-109">Return Value</span></span>  
 <span data-ttu-id="b4208-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b4208-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4208-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4208-111">Requirements</span></span>  
 <span data-ttu-id="b4208-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="b4208-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4208-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4208-113">See also</span></span>

- [<span data-ttu-id="b4208-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4208-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b4208-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4208-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b4208-116">ALink-API</span><span class="sxs-lookup"><span data-stu-id="b4208-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
