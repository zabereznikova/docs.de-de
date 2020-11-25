---
title: ImportTypes-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 762f78900add70238971978ceecda089d0c725ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705110"
---
# <a name="importtypes-method"></a><span data-ttu-id="ca513-102">ImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="ca513-102">ImportTypes Method</span></span>

<span data-ttu-id="ca513-103">Initiiert den Import von Typen aus jedem Bereich, der über die [ImportFile-Methode](importfile-method.md)importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ca513-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca513-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca513-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca513-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca513-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="ca513-106">Die ID der Assembly, in die importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca513-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ca513-107">Die ID der Datei, aus der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca513-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="ca513-108">NULL basierter Gültigkeitsbereich, der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca513-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="ca513-109">Empfängt das Enumeratorhandle für die Typen in diesem Bereich.</span><span class="sxs-lookup"><span data-stu-id="ca513-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="ca513-110">Empfängt optional die [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ca513-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="ca513-111">Empfängt optional die Anzahl der Typen im aufgeführten Bereich.</span><span class="sxs-lookup"><span data-stu-id="ca513-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca513-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca513-112">Return Value</span></span>  

 <span data-ttu-id="ca513-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ca513-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca513-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ca513-114">Requirements</span></span>  

 <span data-ttu-id="ca513-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="ca513-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca513-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca513-116">See also</span></span>

- [<span data-ttu-id="ca513-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca513-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ca513-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca513-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ca513-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="ca513-119">ALink API</span></span>](index.md)
