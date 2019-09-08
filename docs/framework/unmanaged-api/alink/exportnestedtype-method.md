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
ms.openlocfilehash: 570e48788a11045882ef546bf6bc22315c2a02b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777275"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="6aac9-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="6aac9-102">ExportNestedType Method</span></span>
<span data-ttu-id="6aac9-103">Gibt die zu exportierenden Typen als exportierbar an.</span><span class="sxs-lookup"><span data-stu-id="6aac9-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="6aac9-104">Die [ExportType-Methode](exporttype-method.md) kann auch die in die Liste eingefügten Typen exportieren, diese Methode ist jedoch schneller.</span><span class="sxs-lookup"><span data-stu-id="6aac9-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aac9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6aac9-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6aac9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6aac9-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6aac9-107">Die ID der zu exportierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="6aac9-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6aac9-108">Dateitoken oder Assemblydatei, die den Typ definiert, der exportierbar gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="6aac9-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="6aac9-109">Typtoken vom Typ, das als exportierbar erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6aac9-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="6aac9-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="6aac9-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="6aac9-111">Der voll qualifizierte Typname, der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6aac9-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6aac9-112">`ComType`Flags wie `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="6aac9-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="6aac9-113">Dieser Wert kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="6aac9-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="6aac9-114">Empfängt das Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="6aac9-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6aac9-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6aac9-115">Return Value</span></span>  
 <span data-ttu-id="6aac9-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6aac9-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aac9-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6aac9-117">Requirements</span></span>  
 <span data-ttu-id="6aac9-118">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="6aac9-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aac9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6aac9-119">See also</span></span>

- [<span data-ttu-id="6aac9-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6aac9-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6aac9-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6aac9-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6aac9-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="6aac9-122">ALink API</span></span>](index.md)
