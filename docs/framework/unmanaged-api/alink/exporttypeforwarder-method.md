---
title: ExportTypeForwarder-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f97f46595f43c7576c499c6b9944f7e3509662fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742007"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="596d9-102">ExportTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="596d9-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="596d9-103">Fügt eine typweiterleitung zur Typtabelle der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="596d9-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="596d9-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="596d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="596d9-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="596d9-106">Verweis auf die Assembly, die auf der die typweiterleitung verweist.</span><span class="sxs-lookup"><span data-stu-id="596d9-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="596d9-107">Vollqualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="596d9-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="596d9-108">`ComType` Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="596d9-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="596d9-109">Dieser Wert kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="596d9-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="596d9-110">Empfängt das Token des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="596d9-110">Receives the token of the exported type.</span></span> <span data-ttu-id="596d9-111">Dies ist nur für die Ausgabe von geschachtelter Typen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="596d9-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="596d9-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="596d9-112">Return Value</span></span>  
 <span data-ttu-id="596d9-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="596d9-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="596d9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="596d9-114">Requirements</span></span>  
 <span data-ttu-id="596d9-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="596d9-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="596d9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="596d9-116">See also</span></span>

- [<span data-ttu-id="596d9-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="596d9-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="596d9-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="596d9-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="596d9-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="596d9-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
