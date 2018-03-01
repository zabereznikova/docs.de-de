---
title: ExportTypeForwarder-Methode
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
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3fe418b1f8a5d5a6d3c2d36184ca76d5ef9989bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="b70e2-102">ExportTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="b70e2-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="b70e2-103">Die Tabelle der angegebenen Assembly hinzugefügt typweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="b70e2-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b70e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b70e2-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b70e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b70e2-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="b70e2-106">Verweis auf die Assembly, auf die die typweiterleitung verweist.</span><span class="sxs-lookup"><span data-stu-id="b70e2-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="b70e2-107">Voll qualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="b70e2-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b70e2-108">`ComType`Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="b70e2-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="b70e2-109">Dieser Wert möglicherweise übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="b70e2-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="b70e2-110">Empfängt das Token des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="b70e2-110">Receives the token of the exported type.</span></span> <span data-ttu-id="b70e2-111">Dies ist nur für das Ausgeben von geschachtelten Typen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b70e2-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b70e2-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b70e2-112">Return Value</span></span>  
 <span data-ttu-id="b70e2-113">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b70e2-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b70e2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b70e2-114">Requirements</span></span>  
 <span data-ttu-id="b70e2-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="b70e2-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b70e2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b70e2-116">See Also</span></span>  
 [<span data-ttu-id="b70e2-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b70e2-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b70e2-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b70e2-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b70e2-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="b70e2-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
