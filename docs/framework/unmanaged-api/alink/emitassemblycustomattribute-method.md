---
title: EmitAssemblyCustomAttribute-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf2c3dcaf16e949f8770121d8324cbfe6c7d05b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404078"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="2776a-102">EmitAssemblyCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="2776a-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="2776a-103">Der Aufruf zum Festlegen der benutzerdefinierter Attributen auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="2776a-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2776a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2776a-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="2776a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2776a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2776a-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="2776a-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2776a-107">Datei, die das Attribut definiert.</span><span class="sxs-lookup"><span data-stu-id="2776a-107">File that defiles the attribute.</span></span> <span data-ttu-id="2776a-108">Kann NULL sein, wenn `AssemblyID` einen ungebundenen NETMODULE-Datei nicht an.</span><span class="sxs-lookup"><span data-stu-id="2776a-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="2776a-109">Der Typ des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="2776a-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="2776a-110">Daten mit benutzerdefinierten Werten.</span><span class="sxs-lookup"><span data-stu-id="2776a-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="2776a-111">Die Länge der Daten mit benutzerdefinierten Werten.</span><span class="sxs-lookup"><span data-stu-id="2776a-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="2776a-112">"True", wenn das benutzerdefinierte Attribut zum Signieren der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="2776a-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="2776a-113">True, wenn mehrere Attribute ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2776a-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2776a-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2776a-114">Return Value</span></span>  
 <span data-ttu-id="2776a-115">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2776a-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2776a-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2776a-116">Requirements</span></span>  
 <span data-ttu-id="2776a-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="2776a-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2776a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2776a-118">See Also</span></span>  
 [<span data-ttu-id="2776a-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2776a-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="2776a-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2776a-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="2776a-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2776a-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
