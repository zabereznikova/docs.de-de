---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 635792962e259f181a1ff3e0c46438951e4223db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="b6127-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode-Methode</span><span class="sxs-lookup"><span data-stu-id="b6127-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="b6127-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b6127-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b6127-104">Konfiguriert, wie der Debugger speicherinterne Aktualisierungen von Metadaten innerhalb des Zielprozesses behandelt.</span><span class="sxs-lookup"><span data-stu-id="b6127-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6127-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6127-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6127-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6127-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="b6127-107">Ein [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) -Enumerationswert ab, der angibt, ob speicherinterne Aktualisierungen von Metadaten im Zielprozess sichtbar sind (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) oder nicht sichtbar (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="b6127-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6127-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6127-108">Remarks</span></span>  
 <span data-ttu-id="b6127-109">Aktualisierungen von Metadaten im Zielprozess können durch Bearbeiten und Fortfahren, einen Profiler oder <xref:System.Reflection.Emit?displayProperty=nameWithType> ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b6127-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6127-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6127-110">Requirements</span></span>  
 <span data-ttu-id="b6127-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6127-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6127-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6127-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6127-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6127-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6127-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6127-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6127-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6127-115">See Also</span></span>  
 [<span data-ttu-id="b6127-116">ICorDebugProcess7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6127-116">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [<span data-ttu-id="b6127-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b6127-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
