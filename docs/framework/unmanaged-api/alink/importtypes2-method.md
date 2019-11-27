---
title: ImportTypes2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: 8dae903ab76ab83ac0818c4bc4a76e81094bdf65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445663"
---
# <a name="importtypes2-method"></a><span data-ttu-id="891dc-102">ImportTypes2-Methode</span><span class="sxs-lookup"><span data-stu-id="891dc-102">ImportTypes2 Method</span></span>
<span data-ttu-id="891dc-103">Initiiert den Import von-Typen.</span><span class="sxs-lookup"><span data-stu-id="891dc-103">Initiates the import of types.</span></span> <span data-ttu-id="891dc-104">Mit dieser Methode können Sie beginnen, Typen aus jedem Bereich zu importieren, der über die [ImportFile-Methode](importfile-method.md)importiert wird</span><span class="sxs-lookup"><span data-stu-id="891dc-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="891dc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="891dc-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="891dc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="891dc-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="891dc-107">Die ID der Assembly, in die importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="891dc-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="891dc-108">Die ID der Datei, aus der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="891dc-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="891dc-109">NULL basierter Bereich, aus dem importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="891dc-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="891dc-110">Empfängt das Enumeratorhandle für die Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="891dc-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="891dc-111">Empfängt optional die [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="891dc-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="891dc-112">Empfängt optional die Anzahl der Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="891dc-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="891dc-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="891dc-113">Return Value</span></span>  
 <span data-ttu-id="891dc-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="891dc-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="891dc-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="891dc-115">Requirements</span></span>  
 <span data-ttu-id="891dc-116">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="891dc-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891dc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="891dc-117">See also</span></span>

- [<span data-ttu-id="891dc-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="891dc-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="891dc-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="891dc-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="891dc-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="891dc-120">ALink API</span></span>](index.md)
