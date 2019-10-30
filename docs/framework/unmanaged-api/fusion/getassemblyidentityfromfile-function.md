---
title: GetAssemblyIdentityFromFile-Funktion
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 50ec5a23db4d2460480bcc3e463ecd88e7470bde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134524"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="585ce-102">GetAssemblyIdentityFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="585ce-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="585ce-103">Ruft einen Zeiger auf ein `IUnknown`-Objekt mit dem angegebenen `IID` in der Assembly am angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="585ce-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="585ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="585ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="585ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="585ce-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="585ce-106">in Ein gültiger Pfad zur angeforderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="585ce-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="585ce-107">in Der `IID` der zurück zugebende Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="585ce-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="585ce-108">vorgenommen Der zurückgegebene Schnittstellen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="585ce-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585ce-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="585ce-109">Requirements</span></span>  
 <span data-ttu-id="585ce-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="585ce-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585ce-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="585ce-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="585ce-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585ce-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585ce-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="585ce-113">See also</span></span>

- [<span data-ttu-id="585ce-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="585ce-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="585ce-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="585ce-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
