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
ms.openlocfilehash: 69c99e2facfcb9077c3fc4131186ba3882c7cef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684836"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="3ff9d-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="3ff9d-102">ExportNestedType Method</span></span>

<span data-ttu-id="3ff9d-103">Gibt die zu exportierenden Typen als exportierbar an.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="3ff9d-104">Die [ExportType-Methode](exporttype-method.md) kann auch die in die Liste eingefügten Typen exportieren, diese Methode ist jedoch schneller.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff9d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ff9d-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3ff9d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ff9d-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="3ff9d-107">Die ID der zu exportierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3ff9d-108">Dateitoken oder Assemblydatei, die den Typ definiert, der exportierbar gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="3ff9d-109">Typtoken vom Typ, das als exportierbar erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="3ff9d-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3ff9d-111">Der voll qualifizierte Typname, der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3ff9d-112">`ComType` Flags wie `tdPublic` oder `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="3ff9d-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="3ff9d-113">Dieser Wert kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="3ff9d-114">Empfängt das Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ff9d-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ff9d-115">Return Value</span></span>  

 <span data-ttu-id="3ff9d-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3ff9d-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ff9d-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3ff9d-117">Requirements</span></span>  

 <span data-ttu-id="3ff9d-118">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="3ff9d-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff9d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ff9d-119">See also</span></span>

- [<span data-ttu-id="3ff9d-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ff9d-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3ff9d-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ff9d-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3ff9d-122">ALink-API</span><span class="sxs-lookup"><span data-stu-id="3ff9d-122">ALink API</span></span>](index.md)
