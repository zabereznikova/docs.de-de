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
ms.openlocfilehash: 7dfaedad48291ac09f6959bc7b314ae0d9da76e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742046"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="ef9a0-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="ef9a0-102">ExportNestedType Method</span></span>
<span data-ttu-id="ef9a0-103">Gibt geschachtelte Typen als "Exportierbar" markieren.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="ef9a0-104">Die [ExportType-Methode](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef9a0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef9a0-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ef9a0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef9a0-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ef9a0-107">ID der Assembly zum Exportieren aus.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ef9a0-108">Datei-Token oder übergeordnete Assembly der Datei, definiert den Typ als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="ef9a0-109">Geben Sie ein Token des Typs als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="ef9a0-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="ef9a0-111">Vollqualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ef9a0-112">`ComType` Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="ef9a0-113">Dieser Wert kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="ef9a0-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="ef9a0-114">Empfängt die Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef9a0-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ef9a0-115">Return Value</span></span>  
 <span data-ttu-id="ef9a0-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ef9a0-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef9a0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef9a0-117">Requirements</span></span>  
 <span data-ttu-id="ef9a0-118">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="ef9a0-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9a0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef9a0-119">See also</span></span>

- [<span data-ttu-id="ef9a0-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef9a0-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ef9a0-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef9a0-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ef9a0-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ef9a0-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
