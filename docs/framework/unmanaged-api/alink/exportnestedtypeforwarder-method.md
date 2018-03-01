---
title: ExportNestedTypeForwarder-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eee41e9f71d600a74cc9f74b538ad9e215f0d905
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="5eae8-102">ExportNestedTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="5eae8-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="5eae8-103">Die Tabelle der angegebenen Assembly hinzugefügt typweiterleitung für einen geschachtelten Typ.</span><span class="sxs-lookup"><span data-stu-id="5eae8-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eae8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5eae8-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="5eae8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5eae8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5eae8-106">Die ID der Assembly exportieren.</span><span class="sxs-lookup"><span data-stu-id="5eae8-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="5eae8-107">Datei-Token oder Assembly-ID der Datei, die den Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="5eae8-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="5eae8-108">Token für den Typ.</span><span class="sxs-lookup"><span data-stu-id="5eae8-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="5eae8-109">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="5eae8-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="5eae8-110">Voll qualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="5eae8-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5eae8-111">`ComType`Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="5eae8-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="5eae8-112">Empfängt Token Exporttyp an.</span><span class="sxs-lookup"><span data-stu-id="5eae8-112">Receives token of export type.</span></span> <span data-ttu-id="5eae8-113">Dies ist nur für das Ausgeben von geschachtelten Typen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5eae8-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5eae8-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5eae8-114">Return Value</span></span>  
 <span data-ttu-id="5eae8-115">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5eae8-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eae8-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5eae8-116">Requirements</span></span>  
 <span data-ttu-id="5eae8-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="5eae8-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eae8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5eae8-118">See Also</span></span>  
 [<span data-ttu-id="5eae8-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5eae8-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5eae8-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5eae8-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5eae8-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="5eae8-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
