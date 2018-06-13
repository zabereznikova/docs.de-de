---
title: ExportNestedTypeForwarder-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dfb31a2fad8a07b3821ac85bbb43b25693f11d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404098"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="a144b-102">ExportNestedTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="a144b-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="a144b-103">Die Tabelle der angegebenen Assembly hinzugefügt typweiterleitung für einen geschachtelten Typ.</span><span class="sxs-lookup"><span data-stu-id="a144b-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a144b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a144b-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a144b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a144b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a144b-106">Die ID der Assembly exportieren.</span><span class="sxs-lookup"><span data-stu-id="a144b-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a144b-107">Datei-Token oder Assembly-ID der Datei, die den Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="a144b-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="a144b-108">Token für den Typ.</span><span class="sxs-lookup"><span data-stu-id="a144b-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="a144b-109">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="a144b-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="a144b-110">Voll qualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="a144b-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a144b-111">`ComType` Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="a144b-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="a144b-112">Empfängt Token Exporttyp an.</span><span class="sxs-lookup"><span data-stu-id="a144b-112">Receives token of export type.</span></span> <span data-ttu-id="a144b-113">Dies ist nur für das Ausgeben von geschachtelten Typen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a144b-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a144b-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a144b-114">Return Value</span></span>  
 <span data-ttu-id="a144b-115">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a144b-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a144b-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a144b-116">Requirements</span></span>  
 <span data-ttu-id="a144b-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="a144b-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a144b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a144b-118">See Also</span></span>  
 [<span data-ttu-id="a144b-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a144b-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a144b-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a144b-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a144b-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a144b-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
