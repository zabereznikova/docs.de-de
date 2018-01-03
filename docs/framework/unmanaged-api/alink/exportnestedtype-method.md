---
title: ExportNestedType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedType
helpviewer_keywords: ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6d40fffb2d40012d69599ad1bfcdbdaf454aa02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="1524b-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="1524b-102">ExportNestedType Method</span></span>
<span data-ttu-id="1524b-103">Gibt geschachtelte Typen als "Exportierbar" markieren.</span><span class="sxs-lookup"><span data-stu-id="1524b-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="1524b-104">Die [ExportType-Methode](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.</span><span class="sxs-lookup"><span data-stu-id="1524b-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1524b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1524b-105">Syntax</span></span>  
  
```  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="1524b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1524b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1524b-107">ID der Assembly exportieren.</span><span class="sxs-lookup"><span data-stu-id="1524b-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1524b-108">Datei-Token oder übergeordnete Assembly der Datei, definiert den Typ als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1524b-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="1524b-109">Geben Sie ein Token vom Typ als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1524b-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="1524b-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="1524b-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="1524b-111">Voll qualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="1524b-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1524b-112">`ComType`Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="1524b-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="1524b-113">Dieser Wert möglicherweise übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="1524b-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="1524b-114">Empfängt Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="1524b-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1524b-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1524b-115">Return Value</span></span>  
 <span data-ttu-id="1524b-116">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1524b-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1524b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1524b-117">Requirements</span></span>  
 <span data-ttu-id="1524b-118">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="1524b-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1524b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1524b-119">See Also</span></span>  
 [<span data-ttu-id="1524b-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1524b-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1524b-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1524b-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1524b-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="1524b-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
