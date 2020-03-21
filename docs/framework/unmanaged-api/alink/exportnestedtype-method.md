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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179412"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="f73bf-102">ExportNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="f73bf-102">ExportNestedType Method</span></span>
<span data-ttu-id="f73bf-103">Gibt geschachtelte Typen als exportierbar an.</span><span class="sxs-lookup"><span data-stu-id="f73bf-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="f73bf-104">Die [ExportType-Methode](exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.</span><span class="sxs-lookup"><span data-stu-id="f73bf-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f73bf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f73bf-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f73bf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f73bf-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f73bf-107">ID der Assembly, aus der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f73bf-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f73bf-108">Dateitoken oder Assembly der Datei, die den Typ definiert, der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f73bf-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="f73bf-109">Typtoken des Typs, der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f73bf-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="f73bf-110">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="f73bf-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="f73bf-111">Vollständig qualifizierter Typname zum Exportieren.</span><span class="sxs-lookup"><span data-stu-id="f73bf-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f73bf-112">`ComType`Flags wie `tdPublic` `tdNested`oder .</span><span class="sxs-lookup"><span data-stu-id="f73bf-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="f73bf-113">Dieser Wert kann an [defineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f73bf-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="f73bf-114">Empfängt Token für exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="f73bf-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f73bf-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f73bf-115">Return Value</span></span>  
 <span data-ttu-id="f73bf-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f73bf-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f73bf-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f73bf-117">Requirements</span></span>  
 <span data-ttu-id="f73bf-118">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="f73bf-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f73bf-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f73bf-119">See also</span></span>

- [<span data-ttu-id="f73bf-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f73bf-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f73bf-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f73bf-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f73bf-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="f73bf-122">ALink API</span></span>](index.md)
