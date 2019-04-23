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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220083"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="cec05-102">ExportNestedTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="cec05-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="cec05-103">Fügt eine typweiterleitung für einen geschachtelten Typ der Typtabelle der angegebenen Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="cec05-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cec05-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="cec05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cec05-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cec05-106">Die ID der Assembly zum Exportieren aus.</span><span class="sxs-lookup"><span data-stu-id="cec05-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cec05-107">Datei-Token "oder" Assembly-ID der Datei, die den Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="cec05-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="cec05-108">Token für den Typ.</span><span class="sxs-lookup"><span data-stu-id="cec05-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="cec05-109">Token des übergeordneten Typs.</span><span class="sxs-lookup"><span data-stu-id="cec05-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="cec05-110">Vollqualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="cec05-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cec05-111">`ComType` Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="cec05-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="cec05-112">Empfängt die Token des Exporttyps.</span><span class="sxs-lookup"><span data-stu-id="cec05-112">Receives token of export type.</span></span> <span data-ttu-id="cec05-113">Dies ist nur für die Ausgabe von geschachtelter Typen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cec05-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cec05-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cec05-114">Return Value</span></span>  
 <span data-ttu-id="cec05-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="cec05-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cec05-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cec05-116">Requirements</span></span>  
 <span data-ttu-id="cec05-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="cec05-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec05-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cec05-118">See also</span></span>

- [<span data-ttu-id="cec05-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cec05-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cec05-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cec05-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cec05-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="cec05-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
