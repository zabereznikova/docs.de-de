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
ms.openlocfilehash: af040c4a6c9b85930d2d9261f8587ba69eb204e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721477"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="de474-102">GetAssemblyRefHash-Methode</span><span class="sxs-lookup"><span data-stu-id="de474-102">GetAssemblyRefHash Method</span></span>

<span data-ttu-id="de474-103">Ruft ein hashblob für eine angegebene Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="de474-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de474-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de474-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="de474-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de474-105">Parameters</span></span>  

 `FileToken`  
 <span data-ttu-id="de474-106">Die ID der Assembly, auf die der Hash verweist.</span><span class="sxs-lookup"><span data-stu-id="de474-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="de474-107">Empfängt das resultierende hashblob.</span><span class="sxs-lookup"><span data-stu-id="de474-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="de474-108">Empfängt die Größe des hashblobs in Byte.</span><span class="sxs-lookup"><span data-stu-id="de474-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de474-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de474-109">Return Value</span></span>  

 <span data-ttu-id="de474-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="de474-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de474-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="de474-111">Requirements</span></span>  

 <span data-ttu-id="de474-112">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="de474-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de474-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de474-113">See also</span></span>

- [<span data-ttu-id="de474-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de474-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="de474-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de474-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="de474-116">ALink-API</span><span class="sxs-lookup"><span data-stu-id="de474-116">ALink API</span></span>](index.md)
