---
title: IAssemblyCache::QueryAssemblyInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66e09f805b120239eef764b8cd61835e713e236c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="2a2b6-102">IAssemblyCache::QueryAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="2a2b6-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="2a2b6-103">Ruft die angeforderten Daten über die angegebene Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="2a2b6-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a2b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a2b6-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a2b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a2b6-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="2a2b6-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2a2b6-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="2a2b6-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2a2b6-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="2a2b6-108">QUERYASMINFO_FLAG_VALIDATE (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="2a2b6-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="2a2b6-109">QUERYASMINFO_FLAG_GETSIZE (0 X 00000002)</span><span class="sxs-lookup"><span data-stu-id="2a2b6-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="2a2b6-110">[in] Der Name der Assembly, die für die Daten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2a2b6-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="2a2b6-111">[in, out] Ein [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) -Struktur, die Daten über die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="2a2b6-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a2b6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a2b6-112">Requirements</span></span>  
 <span data-ttu-id="2a2b6-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a2b6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a2b6-114">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="2a2b6-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2a2b6-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a2b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2b6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a2b6-116">See Also</span></span>  
 [<span data-ttu-id="2a2b6-117">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a2b6-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
