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
ms.openlocfilehash: 2070d1ec2aec80638c20c764eed5086c4a42e0fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676360"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="fb4c6-102">EmitAssemblyCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="fb4c6-102">EmitAssemblyCustomAttribute Method</span></span>

<span data-ttu-id="fb4c6-103">Aufgerufen, um benutzerdefinierte Attribute auf Assemblyebene festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb4c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb4c6-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="fb4c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb4c6-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="fb4c6-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fb4c6-107">Die Datei, die das Attribut deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-107">File that defiles the attribute.</span></span> <span data-ttu-id="fb4c6-108">Kann NULL sein, wenn `AssemblyID` kein ungebundenes NetModule angibt.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="fb4c6-109">Der Typ des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="fb4c6-110">Benutzerdefinierte Wertdaten.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="fb4c6-111">Länge von benutzerdefinierten Wertdaten.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="fb4c6-112">TRUE, wenn das benutzerdefinierte Attribut mit der Assemblysignatur verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="fb4c6-113">TRUE, wenn mehrere Attribute ausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb4c6-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fb4c6-114">Return Value</span></span>  

 <span data-ttu-id="fb4c6-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="fb4c6-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb4c6-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fb4c6-116">Requirements</span></span>  

 <span data-ttu-id="fb4c6-117">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="fb4c6-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb4c6-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb4c6-118">See also</span></span>

- [<span data-ttu-id="fb4c6-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb4c6-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fb4c6-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb4c6-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fb4c6-121">ALink-API</span><span class="sxs-lookup"><span data-stu-id="fb4c6-121">ALink API</span></span>](index.md)
