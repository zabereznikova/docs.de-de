---
title: ICorDebugMergedAssemblyRecord::GetSimpleName-Methode
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: f6c6682c8bb23143d308aa4f1a6887b28ea82fcd
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209707"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="df3e1-102">ICorDebugMergedAssemblyRecord::GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="df3e1-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="df3e1-103">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="df3e1-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df3e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df3e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df3e1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df3e1-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="df3e1-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="df3e1-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="df3e1-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df3e1-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="df3e1-108">Ein Zeiger auf ein Zeichenarray.</span><span class="sxs-lookup"><span data-stu-id="df3e1-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df3e1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df3e1-109">Remarks</span></span>  
 <span data-ttu-id="df3e1-110">Diese Methode ruft den einfachen Namen einer Assembly (z. B. "System.Collections") ohne eine Dateierweiterung, eine Version, eine Kultur oder ein öffentliches Schlüsseltoken ab.</span><span class="sxs-lookup"><span data-stu-id="df3e1-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="df3e1-111">Sie entspricht der Eigenschaft <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="df3e1-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df3e1-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df3e1-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df3e1-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df3e1-113">Requirements</span></span>  
 <span data-ttu-id="df3e1-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df3e1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df3e1-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df3e1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df3e1-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df3e1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df3e1-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df3e1-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3e1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df3e1-118">See also</span></span>

- [<span data-ttu-id="df3e1-119">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df3e1-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="df3e1-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="df3e1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
