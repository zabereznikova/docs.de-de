---
title: ExportNestedTypeForwarder-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: cc81ccd1c754e3d34c54737f4560b4f81d5cc916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438413"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="2c440-102">ExportNestedTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="2c440-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="2c440-103">Fügt der Typtabelle der angegebenen Assembly eine Typweiterleitung für einen geblierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c440-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c440-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c440-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="2c440-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c440-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2c440-106">Die ID der Assembly, aus der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c440-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2c440-107">Dateitoken oder Assembly-ID der Datei, die den Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="2c440-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="2c440-108">Token für den Typ.</span><span class="sxs-lookup"><span data-stu-id="2c440-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="2c440-109">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="2c440-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="2c440-110">Der voll qualifizierte Typname, der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c440-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2c440-111">`ComType` Flags, z. b. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="2c440-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="2c440-112">Empfängt das Token des Export Typs.</span><span class="sxs-lookup"><span data-stu-id="2c440-112">Receives token of export type.</span></span> <span data-ttu-id="2c440-113">Dies ist nur für das Ausgeben von Untertypen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c440-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c440-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c440-114">Return Value</span></span>  
 <span data-ttu-id="2c440-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2c440-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c440-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2c440-116">Requirements</span></span>  
 <span data-ttu-id="2c440-117">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="2c440-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c440-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c440-118">See also</span></span>

- [<span data-ttu-id="2c440-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c440-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2c440-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c440-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2c440-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2c440-121">ALink API</span></span>](index.md)
