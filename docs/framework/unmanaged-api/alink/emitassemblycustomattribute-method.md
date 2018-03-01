---
title: EmitAssemblyCustomAttribute-Methode
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
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9cc7709ef060642f12a8bc7d048e520427a5c674
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="0fa6e-102">EmitAssemblyCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="0fa6e-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="0fa6e-103">Der Aufruf zum Festlegen der benutzerdefinierter Attributen auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fa6e-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fa6e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0fa6e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0fa6e-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0fa6e-107">Datei, die das Attribut definiert.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-107">File that defiles the attribute.</span></span> <span data-ttu-id="0fa6e-108">Kann NULL sein, wenn `AssemblyID` einen ungebundenen NETMODULE-Datei nicht an.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="0fa6e-109">Der Typ des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="0fa6e-110">Daten mit benutzerdefinierten Werten.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="0fa6e-111">Die Länge der Daten mit benutzerdefinierten Werten.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="0fa6e-112">"True", wenn das benutzerdefinierte Attribut zum Signieren der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="0fa6e-113">True, wenn mehrere Attribute ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fa6e-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0fa6e-114">Return Value</span></span>  
 <span data-ttu-id="0fa6e-115">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fa6e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0fa6e-116">Requirements</span></span>  
 <span data-ttu-id="0fa6e-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="0fa6e-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa6e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fa6e-118">See Also</span></span>  
 [<span data-ttu-id="0fa6e-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0fa6e-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0fa6e-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0fa6e-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0fa6e-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="0fa6e-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
