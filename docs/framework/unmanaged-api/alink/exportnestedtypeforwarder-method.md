---
title: ExportNestedTypeForwarder-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportNestedTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedTypeForwarder
helpviewer_keywords: ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 41c0984e4439b89ddee2b55bbca7a098075d6bd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="7d1ef-102">ExportNestedTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="7d1ef-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="7d1ef-103">Die Tabelle der angegebenen Assembly hinzugefügt typweiterleitung für einen geschachtelten Typ.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d1ef-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="7d1ef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d1ef-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7d1ef-106">Die ID der Assembly exportieren.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7d1ef-107">Datei-Token oder Assembly-ID der Datei, die den Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="7d1ef-108">Token für den Typ.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="7d1ef-109">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="7d1ef-110">Voll qualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7d1ef-111">`ComType`Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="7d1ef-112">Empfängt Token Exporttyp an.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-112">Receives token of export type.</span></span> <span data-ttu-id="7d1ef-113">Dies ist nur für das Ausgeben von geschachtelten Typen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d1ef-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d1ef-114">Return Value</span></span>  
 <span data-ttu-id="7d1ef-115">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7d1ef-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d1ef-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d1ef-116">Requirements</span></span>  
 <span data-ttu-id="7d1ef-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="7d1ef-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1ef-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d1ef-118">See Also</span></span>  
 [<span data-ttu-id="7d1ef-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d1ef-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="7d1ef-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d1ef-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="7d1ef-121">ALink-API</span><span class="sxs-lookup"><span data-stu-id="7d1ef-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
