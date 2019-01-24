---
title: SetPEKind-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fe770ffc5a9c187e9069e8a66553976f9a53b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709883"
---
# <a name="setpekind-method"></a><span data-ttu-id="84c6c-102">SetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="84c6c-102">SetPEKind Method</span></span>
<span data-ttu-id="84c6c-103">Bestimmt den portable ausführbare Typ, entweder computerspezifischen oder Computer agnostisch.</span><span class="sxs-lookup"><span data-stu-id="84c6c-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84c6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84c6c-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="84c6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84c6c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="84c6c-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="84c6c-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="84c6c-107">Token der Datei, die für die PE-Typ ist, festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="84c6c-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="84c6c-108">Kann NULL sein, wenn `AssemblyID` gibt nicht an eine nicht gebundene NETMODULE-Datei.</span><span class="sxs-lookup"><span data-stu-id="84c6c-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="84c6c-109">Der Typ von PE, wie durch die [CorPEKind-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="84c6c-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="84c6c-110">Die Architektur des Zielcomputers, wie in der NT-Header angegeben.</span><span class="sxs-lookup"><span data-stu-id="84c6c-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84c6c-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84c6c-111">Return Value</span></span>  
 <span data-ttu-id="84c6c-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="84c6c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84c6c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84c6c-113">Requirements</span></span>  
 <span data-ttu-id="84c6c-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="84c6c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c6c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84c6c-115">See also</span></span>
- [<span data-ttu-id="84c6c-116">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="84c6c-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="84c6c-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84c6c-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="84c6c-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84c6c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="84c6c-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="84c6c-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
