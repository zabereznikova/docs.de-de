---
title: SetPEKind-Methode
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
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ad300d86dadd470d0a2d50d5d6deac5bd0bad71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="setpekind-method"></a><span data-ttu-id="96930-102">SetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="96930-102">SetPEKind Method</span></span>
<span data-ttu-id="96930-103">Bestimmt den portable ausführbare Typ, computerspezifischen oder Unabhängigkeit von der Maschine.</span><span class="sxs-lookup"><span data-stu-id="96930-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96930-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96930-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="96930-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="96930-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="96930-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="96930-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="96930-107">Datei für das Token ist der PE-Typ festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="96930-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="96930-108">Kann NULL sein, wenn `AssemblyID` einen ungebundenen NETMODULE-Datei nicht an.</span><span class="sxs-lookup"><span data-stu-id="96930-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="96930-109">Der Typ des PE, durch die [CorPEKind-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="96930-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="96930-110">Die Architektur des Zielcomputers, wie in der NT-Header angegeben.</span><span class="sxs-lookup"><span data-stu-id="96930-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96930-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="96930-111">Return Value</span></span>  
 <span data-ttu-id="96930-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="96930-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96930-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96930-113">Requirements</span></span>  
 <span data-ttu-id="96930-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="96930-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96930-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96930-115">See Also</span></span>  
 [<span data-ttu-id="96930-116">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="96930-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [<span data-ttu-id="96930-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96930-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="96930-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96930-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="96930-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="96930-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
