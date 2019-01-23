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
ms.openlocfilehash: 7b4909ae23d077ee079e062d0252dbf1ee11663c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538829"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="ee565-102">EmitAssemblyCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="ee565-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="ee565-103">Der Aufruf zum Festlegen der benutzerdefinierten Attribute auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="ee565-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee565-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee565-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ee565-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee565-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ee565-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ee565-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ee565-107">Datei, die das Attribut definiert.</span><span class="sxs-lookup"><span data-stu-id="ee565-107">File that defiles the attribute.</span></span> <span data-ttu-id="ee565-108">Kann NULL sein, wenn `AssemblyID` gibt nicht an eine nicht gebundene NETMODULE-Datei.</span><span class="sxs-lookup"><span data-stu-id="ee565-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ee565-109">Der Typ des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="ee565-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="ee565-110">Benutzerdefinierte-Wert-Daten.</span><span class="sxs-lookup"><span data-stu-id="ee565-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="ee565-111">Länge der Daten mit benutzerdefinierten Werten.</span><span class="sxs-lookup"><span data-stu-id="ee565-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="ee565-112">TRUE, wenn das benutzerdefinierte Attribut zum Signieren der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ee565-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="ee565-113">True, wenn mehrere Attribute, die ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ee565-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee565-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ee565-114">Return Value</span></span>  
 <span data-ttu-id="ee565-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ee565-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee565-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee565-116">Requirements</span></span>  
 <span data-ttu-id="ee565-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="ee565-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee565-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee565-118">See also</span></span>
- [<span data-ttu-id="ee565-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee565-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ee565-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee565-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ee565-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ee565-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
