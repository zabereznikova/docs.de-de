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
ms.openlocfilehash: 5bdf9fb50fe06141df6f3818c784588b9e2138af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212023"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="7d5ad-102">ExportTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5ad-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="7d5ad-103">Fügt eine typweiterleitung zur Typtabelle der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="7d5ad-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d5ad-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d5ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d5ad-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="7d5ad-106">Verweis auf die Assembly, die auf der die typweiterleitung verweist.</span><span class="sxs-lookup"><span data-stu-id="7d5ad-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="7d5ad-107">Vollqualifizierten Typnamen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="7d5ad-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 `ComType` <span data-ttu-id="7d5ad-108">Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="7d5ad-108">flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="7d5ad-109">Dieser Wert kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="7d5ad-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="7d5ad-110">Empfängt das Token des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="7d5ad-110">Receives the token of the exported type.</span></span> <span data-ttu-id="7d5ad-111">Dies ist nur für die Ausgabe von geschachtelter Typen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d5ad-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d5ad-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d5ad-112">Return Value</span></span>  
 <span data-ttu-id="7d5ad-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7d5ad-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5ad-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d5ad-114">Requirements</span></span>  
 <span data-ttu-id="7d5ad-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="7d5ad-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5ad-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d5ad-116">See also</span></span>

- [<span data-ttu-id="7d5ad-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5ad-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7d5ad-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5ad-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7d5ad-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="7d5ad-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
