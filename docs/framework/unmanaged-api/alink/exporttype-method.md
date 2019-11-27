---
title: ExportType-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
ms.openlocfilehash: 84c41e467c57afd2562e7aa8dd72ce4796249667
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438569"
---
# <a name="exporttype-method"></a><span data-ttu-id="7b10d-102">ExportType-Methode</span><span class="sxs-lookup"><span data-stu-id="7b10d-102">ExportType Method</span></span>
<span data-ttu-id="7b10d-103">Gibt an, dass ein Typ exportierbar ist.</span><span class="sxs-lookup"><span data-stu-id="7b10d-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b10d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b10d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b10d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b10d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7b10d-106">Die ID der Assembly, aus der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b10d-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7b10d-107">Dateitoken oder Assembly-ID der Datei, die den exportierbaren Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="7b10d-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="7b10d-108">Das Token vom Typ, das als exportierbar erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b10d-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="7b10d-109">Der voll qualifizierte Typname, der als exportierbar erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b10d-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7b10d-110">`ComType` Flags, z. b. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="7b10d-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="7b10d-111">Dieser Parameter kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="7b10d-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="7b10d-112">Empfängt das Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="7b10d-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b10d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b10d-113">Return Value</span></span>  
 <span data-ttu-id="7b10d-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7b10d-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b10d-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7b10d-115">Requirements</span></span>  
 <span data-ttu-id="7b10d-116">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="7b10d-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b10d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b10d-117">See also</span></span>

- [<span data-ttu-id="7b10d-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b10d-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7b10d-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b10d-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7b10d-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="7b10d-120">ALink API</span></span>](index.md)
