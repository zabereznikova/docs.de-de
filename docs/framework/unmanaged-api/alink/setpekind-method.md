---
title: SetPEKind-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetPEKind
api_location: alink.dll
api_type: COM
f1_keywords: SetPEKind
helpviewer_keywords: SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d511bcda2ab4e879c123d866b3f6c887173c1d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="setpekind-method"></a><span data-ttu-id="ddcc0-102">SetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="ddcc0-102">SetPEKind Method</span></span>
<span data-ttu-id="ddcc0-103">Bestimmt den portable ausführbare Typ, computerspezifischen oder Unabhängigkeit von der Maschine.</span><span class="sxs-lookup"><span data-stu-id="ddcc0-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddcc0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddcc0-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddcc0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ddcc0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ddcc0-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ddcc0-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ddcc0-107">Datei für das Token ist der PE-Typ festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ddcc0-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="ddcc0-108">Kann NULL sein, wenn `AssemblyID` einen ungebundenen NETMODULE-Datei nicht an.</span><span class="sxs-lookup"><span data-stu-id="ddcc0-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="ddcc0-109">Der Typ des PE, durch die [CorPEKind-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ddcc0-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="ddcc0-110">Die Architektur des Zielcomputers, wie in der NT-Header angegeben.</span><span class="sxs-lookup"><span data-stu-id="ddcc0-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddcc0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ddcc0-111">Return Value</span></span>  
 <span data-ttu-id="ddcc0-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ddcc0-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddcc0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ddcc0-113">Requirements</span></span>  
 <span data-ttu-id="ddcc0-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="ddcc0-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddcc0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddcc0-115">See Also</span></span>  
 [<span data-ttu-id="ddcc0-116">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="ddcc0-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [<span data-ttu-id="ddcc0-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ddcc0-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ddcc0-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ddcc0-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ddcc0-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="ddcc0-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
