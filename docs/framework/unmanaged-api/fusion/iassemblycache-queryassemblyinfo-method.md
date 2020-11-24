---
title: IAssemblyCache::QueryAssemblyInfo-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: f764be9b80a8d4dcb15791d406412ece9e7e7c87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670926"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="67e4a-102">IAssemblyCache::QueryAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="67e4a-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>

<span data-ttu-id="67e4a-103">Ruft die angeforderten Daten zur angegebenen Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="67e4a-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67e4a-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67e4a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67e4a-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="67e4a-106">in In Fusion. idl definierte Flags.</span><span class="sxs-lookup"><span data-stu-id="67e4a-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="67e4a-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="67e4a-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="67e4a-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="67e4a-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="67e4a-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="67e4a-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="67e4a-110">in Der Name der Assembly, für die Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="67e4a-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="67e4a-111">[in, out] Eine [ASSEMBLY_INFO](assembly-info-structure.md) -Struktur, die Daten über die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="67e4a-111">[in, out] An [ASSEMBLY_INFO](assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67e4a-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="67e4a-112">Requirements</span></span>  

 <span data-ttu-id="67e4a-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67e4a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e4a-114">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="67e4a-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="67e4a-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e4a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e4a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67e4a-116">See also</span></span>

- [<span data-ttu-id="67e4a-117">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67e4a-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
