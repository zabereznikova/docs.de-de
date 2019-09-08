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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3a0e42e9ffb99896bdd09dbbab65eafb40cafff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777207"
---
# <a name="getscope-method"></a><span data-ttu-id="0629c-102">GetScope-Methode</span><span class="sxs-lookup"><span data-stu-id="0629c-102">GetScope Method</span></span>
<span data-ttu-id="0629c-103">Ruft einen Import Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="0629c-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0629c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0629c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0629c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0629c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0629c-106">Eindeutige ID der Assembly, in die importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0629c-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0629c-107">Eindeutige ID der Datei, aus der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0629c-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="0629c-108">NULL basierter Gültigkeitsbereich, der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0629c-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="0629c-109">Empfängt die [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) -Schnittstelle für den Bereich.</span><span class="sxs-lookup"><span data-stu-id="0629c-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0629c-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0629c-110">Return Value</span></span>  
 <span data-ttu-id="0629c-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="0629c-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0629c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0629c-112">Requirements</span></span>  
 <span data-ttu-id="0629c-113">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="0629c-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0629c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0629c-114">See also</span></span>

- [<span data-ttu-id="0629c-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0629c-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0629c-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0629c-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0629c-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="0629c-117">ALink API</span></span>](index.md)
