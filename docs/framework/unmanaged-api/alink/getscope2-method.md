---
title: GetScope2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: e8c6fd7dca13afe7504e447caca9a217c8136c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684524"
---
# <a name="getscope2-method"></a><span data-ttu-id="c8f0e-102">GetScope2-Methode</span><span class="sxs-lookup"><span data-stu-id="c8f0e-102">GetScope2 Method</span></span>

<span data-ttu-id="c8f0e-103">Ruft einen Import Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8f0e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="c8f0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8f0e-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="c8f0e-106">ID der Zielassembly.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c8f0e-107">Die ID der Datei, aus der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="c8f0e-108">NULL basierter Gültigkeitsbereich, der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="c8f0e-109">Empfängt einen Zeiger auf eine [IMetaDataImport2-Schnittstellen](../metadata/imetadataimport2-interface.md) Schnittstelle für den angegeben Bereich.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8f0e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8f0e-110">Return Value</span></span>  

 <span data-ttu-id="c8f0e-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8f0e-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c8f0e-112">Requirements</span></span>  

 <span data-ttu-id="c8f0e-113">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f0e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8f0e-114">See also</span></span>

- [<span data-ttu-id="c8f0e-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8f0e-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c8f0e-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8f0e-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c8f0e-117">ALink-API</span><span class="sxs-lookup"><span data-stu-id="c8f0e-117">ALink API</span></span>](index.md)
