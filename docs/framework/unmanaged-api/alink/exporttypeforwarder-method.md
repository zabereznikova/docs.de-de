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
ms.openlocfilehash: 36c99477e9faead5e24799d5b0ae8901f1dd13c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448706"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="1a405-102">ExportTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="1a405-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="1a405-103">Fügt der Typtabelle der angegebenen Assembly eine Typweiterleitung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a405-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a405-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a405-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a405-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a405-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="1a405-106">Verweis auf die Assembly, auf die die Typweiterleitung verweist.</span><span class="sxs-lookup"><span data-stu-id="1a405-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="1a405-107">Der voll qualifizierte Typname, der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a405-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1a405-108">`ComType` Flags, z. b. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="1a405-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="1a405-109">Dieser Wert kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="1a405-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="1a405-110">Empfängt das Token des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="1a405-110">Receives the token of the exported type.</span></span> <span data-ttu-id="1a405-111">Dies ist nur für das Ausgeben von Untertypen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1a405-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a405-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1a405-112">Return Value</span></span>  
 <span data-ttu-id="1a405-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="1a405-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a405-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1a405-114">Requirements</span></span>  
 <span data-ttu-id="1a405-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="1a405-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a405-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a405-116">See also</span></span>

- [<span data-ttu-id="1a405-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a405-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1a405-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a405-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1a405-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="1a405-119">ALink API</span></span>](index.md)
