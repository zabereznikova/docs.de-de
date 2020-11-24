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
ms.openlocfilehash: 4e6ceabf37056bfc25247266be2c7801cb0e13e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684771"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="45167-102">ExportTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="45167-102">ExportTypeForwarder Method</span></span>

<span data-ttu-id="45167-103">Fügt der Typtabelle der angegebenen Assembly eine Typweiterleitung hinzu.</span><span class="sxs-lookup"><span data-stu-id="45167-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45167-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45167-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="45167-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45167-105">Parameters</span></span>  

 `tkAssemblyRef`  
 <span data-ttu-id="45167-106">Verweis auf die Assembly, auf die die Typweiterleitung verweist.</span><span class="sxs-lookup"><span data-stu-id="45167-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="45167-107">Der voll qualifizierte Typname, der exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="45167-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="45167-108">`ComType` Flags wie `tdPublic` oder `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="45167-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="45167-109">Dieser Wert kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="45167-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="45167-110">Empfängt das Token des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="45167-110">Receives the token of the exported type.</span></span> <span data-ttu-id="45167-111">Dies ist nur für das Ausgeben von Untertypen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="45167-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45167-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45167-112">Return Value</span></span>  

 <span data-ttu-id="45167-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="45167-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45167-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="45167-114">Requirements</span></span>  

 <span data-ttu-id="45167-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="45167-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45167-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45167-116">See also</span></span>

- [<span data-ttu-id="45167-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45167-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="45167-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45167-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="45167-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="45167-119">ALink API</span></span>](index.md)
