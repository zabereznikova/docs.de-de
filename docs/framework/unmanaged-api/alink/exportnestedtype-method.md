---
title: ExportNestedType-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c7ea671af5c6c725df136810bb8cf6610a6f83f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710338"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="2d1b7-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="2d1b7-102">ExportNestedType Method</span></span>
<span data-ttu-id="2d1b7-103">Gibt geschachtelte Typen als "Exportierbar" markieren.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="2d1b7-104">Die [ExportType-Methode](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1b7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d1b7-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="2d1b7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d1b7-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2d1b7-107">ID der Assembly zum Exportieren aus.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2d1b7-108">Datei-Token oder übergeordnete Assembly der Datei, definiert den Typ als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="2d1b7-109">Geben Sie ein Token des Typs als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="2d1b7-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="2d1b7-111">Vollqualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2d1b7-112">`ComType` Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="2d1b7-113">Dieser Wert kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="2d1b7-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="2d1b7-114">Empfängt die Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d1b7-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d1b7-115">Return Value</span></span>  
 <span data-ttu-id="2d1b7-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2d1b7-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d1b7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d1b7-117">Requirements</span></span>  
 <span data-ttu-id="2d1b7-118">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="2d1b7-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1b7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d1b7-119">See also</span></span>
- [<span data-ttu-id="2d1b7-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d1b7-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2d1b7-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d1b7-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2d1b7-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2d1b7-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
