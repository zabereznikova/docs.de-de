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
ms.openlocfilehash: d19eebaa3aa0ebb6f9807f0cf277b7ed6183c148
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777194"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="09024-102">GetAssemblyRefHash-Methode</span><span class="sxs-lookup"><span data-stu-id="09024-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="09024-103">Ruft ein hashblob für eine angegebene Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="09024-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09024-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09024-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="09024-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="09024-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="09024-106">Die ID der Assembly, auf die der Hash verweist.</span><span class="sxs-lookup"><span data-stu-id="09024-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="09024-107">Empfängt das resultierende hashblob.</span><span class="sxs-lookup"><span data-stu-id="09024-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="09024-108">Empfängt die Größe des hashblobs in Byte.</span><span class="sxs-lookup"><span data-stu-id="09024-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09024-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="09024-109">Return Value</span></span>  
 <span data-ttu-id="09024-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="09024-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09024-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09024-111">Requirements</span></span>  
 <span data-ttu-id="09024-112">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="09024-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09024-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09024-113">See also</span></span>

- [<span data-ttu-id="09024-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09024-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="09024-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09024-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="09024-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="09024-116">ALink API</span></span>](index.md)
