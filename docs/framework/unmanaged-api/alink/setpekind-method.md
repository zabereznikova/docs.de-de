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
ms.openlocfilehash: 4b985aeb97621e552e9e97581e67cae029d019ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405892"
---
# <a name="setpekind-method"></a><span data-ttu-id="83a60-102">SetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="83a60-102">SetPEKind Method</span></span>
<span data-ttu-id="83a60-103">Bestimmt den portable ausführbare Typ, computerspezifischen oder Unabhängigkeit von der Maschine.</span><span class="sxs-lookup"><span data-stu-id="83a60-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83a60-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="83a60-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83a60-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="83a60-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="83a60-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="83a60-107">Datei für das Token ist der PE-Typ festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="83a60-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="83a60-108">Kann NULL sein, wenn `AssemblyID` einen ungebundenen NETMODULE-Datei nicht an.</span><span class="sxs-lookup"><span data-stu-id="83a60-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="83a60-109">Der Typ des PE, durch die [CorPEKind-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="83a60-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="83a60-110">Die Architektur des Zielcomputers, wie in der NT-Header angegeben.</span><span class="sxs-lookup"><span data-stu-id="83a60-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83a60-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83a60-111">Return Value</span></span>  
 <span data-ttu-id="83a60-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="83a60-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83a60-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83a60-113">Requirements</span></span>  
 <span data-ttu-id="83a60-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="83a60-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a60-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83a60-115">See Also</span></span>  
 [<span data-ttu-id="83a60-116">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="83a60-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [<span data-ttu-id="83a60-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83a60-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="83a60-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83a60-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="83a60-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="83a60-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
