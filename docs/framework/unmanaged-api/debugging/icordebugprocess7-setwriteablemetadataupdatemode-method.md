---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a67f93a3f3f75b89bc3f0240995471bc0bf44992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419756"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="50214-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode-Methode</span><span class="sxs-lookup"><span data-stu-id="50214-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="50214-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="50214-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="50214-104">Konfiguriert, wie der Debugger speicherinterne Aktualisierungen von Metadaten innerhalb des Zielprozesses behandelt.</span><span class="sxs-lookup"><span data-stu-id="50214-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50214-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="50214-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50214-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="50214-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="50214-107">Ein [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) -Enumerationswert ab, der angibt, ob speicherinterne Aktualisierungen von Metadaten im Zielprozess sichtbar sind (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) oder nicht sichtbar (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="50214-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50214-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50214-108">Remarks</span></span>  
 <span data-ttu-id="50214-109">Aktualisierungen von Metadaten im Zielprozess können durch Bearbeiten und Fortfahren, einen Profiler oder <xref:System.Reflection.Emit?displayProperty=nameWithType> ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="50214-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50214-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50214-110">Requirements</span></span>  
 <span data-ttu-id="50214-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50214-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50214-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50214-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50214-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50214-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50214-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50214-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50214-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50214-115">See Also</span></span>  
 [<span data-ttu-id="50214-116">ICorDebugProcess7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50214-116">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [<span data-ttu-id="50214-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="50214-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
