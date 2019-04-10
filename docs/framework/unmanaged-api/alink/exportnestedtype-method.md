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
ms.openlocfilehash: ff159cf794d566be6478ef890c769a0ac72c9b25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176604"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="630cc-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="630cc-102">ExportNestedType Method</span></span>
<span data-ttu-id="630cc-103">Gibt geschachtelte Typen als "Exportierbar" markieren.</span><span class="sxs-lookup"><span data-stu-id="630cc-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="630cc-104">Die [ExportType-Methode](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.</span><span class="sxs-lookup"><span data-stu-id="630cc-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="630cc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="630cc-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="630cc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="630cc-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="630cc-107">ID der Assembly zum Exportieren aus.</span><span class="sxs-lookup"><span data-stu-id="630cc-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="630cc-108">Datei-Token oder übergeordnete Assembly der Datei, definiert den Typ als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="630cc-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="630cc-109">Geben Sie ein Token des Typs als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="630cc-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="630cc-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="630cc-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="630cc-111">Vollqualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="630cc-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 `ComType` <span data-ttu-id="630cc-112">Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="630cc-112">flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="630cc-113">Dieser Wert kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="630cc-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="630cc-114">Empfängt die Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="630cc-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="630cc-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="630cc-115">Return Value</span></span>  
 <span data-ttu-id="630cc-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="630cc-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="630cc-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="630cc-117">Requirements</span></span>  
 <span data-ttu-id="630cc-118">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="630cc-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630cc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="630cc-119">See also</span></span>

- [<span data-ttu-id="630cc-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="630cc-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="630cc-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="630cc-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="630cc-122">ALink-API</span><span class="sxs-lookup"><span data-stu-id="630cc-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
