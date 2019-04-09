---
title: CreateInstallReferenceEnum-Funktion
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7820b33dcfacae5ede5235607e40d95940fc474
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092824"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="6711b-102">CreateInstallReferenceEnum-Funktion</span><span class="sxs-lookup"><span data-stu-id="6711b-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="6711b-103">Ruft einen Zeiger auf ein [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) -Instanz, die eine Liste der Verweise einer Anwendung auf die angegebene Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="6711b-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6711b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6711b-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6711b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6711b-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="6711b-106">[out] Das zurückgegebene `IInstallReferenceEnum` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="6711b-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="6711b-107">[in] Die [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) , identifiziert die Assembly, für die Verweise aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6711b-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6711b-108">[in] Flags, die das Verhalten des Enumerators zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="6711b-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6711b-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="6711b-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="6711b-110">ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="6711b-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6711b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6711b-111">Requirements</span></span>  
 <span data-ttu-id="6711b-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6711b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6711b-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="6711b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6711b-114">**Bibliothek:** Fusion.dll und "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="6711b-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="6711b-115">Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="6711b-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="6711b-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6711b-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6711b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6711b-117">See also</span></span>

- [<span data-ttu-id="6711b-118">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6711b-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
- [<span data-ttu-id="6711b-119">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6711b-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="6711b-120">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6711b-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
