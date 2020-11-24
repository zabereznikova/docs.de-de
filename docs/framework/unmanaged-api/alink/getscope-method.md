---
title: GetScope-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: fd5ae6ef40cb171c33132df0f640acbef96d69b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684672"
---
# <a name="getscope-method"></a><span data-ttu-id="62893-102">GetScope-Methode</span><span class="sxs-lookup"><span data-stu-id="62893-102">GetScope Method</span></span>

<span data-ttu-id="62893-103">Ruft einen Import Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="62893-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62893-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62893-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="62893-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62893-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="62893-106">Eindeutige ID der Assembly, in die importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="62893-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="62893-107">Eindeutige ID der Datei, aus der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="62893-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="62893-108">NULL basierter Gültigkeitsbereich, der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="62893-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="62893-109">Empfängt die [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) -Schnittstelle für den Bereich.</span><span class="sxs-lookup"><span data-stu-id="62893-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62893-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62893-110">Return Value</span></span>  

 <span data-ttu-id="62893-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="62893-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62893-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="62893-112">Requirements</span></span>  

 <span data-ttu-id="62893-113">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="62893-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62893-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62893-114">See also</span></span>

- [<span data-ttu-id="62893-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62893-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="62893-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62893-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="62893-117">ALink-API</span><span class="sxs-lookup"><span data-stu-id="62893-117">ALink API</span></span>](index.md)
