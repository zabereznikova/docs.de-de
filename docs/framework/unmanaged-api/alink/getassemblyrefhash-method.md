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
ms.openlocfilehash: c68f43ce2f79ee6e4ec44ce4b2f0dbfb1c1185fa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433872"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="37442-102">GetAssemblyRefHash-Methode</span><span class="sxs-lookup"><span data-stu-id="37442-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="37442-103">Ruft ein hashblob für eine angegebene Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="37442-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37442-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="37442-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37442-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="37442-106">Die ID der Assembly, auf die der Hash verweist.</span><span class="sxs-lookup"><span data-stu-id="37442-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="37442-107">Empfängt das resultierende hashblob.</span><span class="sxs-lookup"><span data-stu-id="37442-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="37442-108">Empfängt die Größe des hashblobs in Byte.</span><span class="sxs-lookup"><span data-stu-id="37442-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37442-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="37442-109">Return Value</span></span>  
 <span data-ttu-id="37442-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="37442-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37442-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="37442-111">Requirements</span></span>  
 <span data-ttu-id="37442-112">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="37442-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37442-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37442-113">See also</span></span>

- [<span data-ttu-id="37442-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37442-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="37442-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37442-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="37442-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="37442-116">ALink API</span></span>](index.md)
