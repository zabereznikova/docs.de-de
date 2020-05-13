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
ms.openlocfilehash: 6de75e1e27660ac91bd6320a501db47f3b055fb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212255"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="41683-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode-Methode</span><span class="sxs-lookup"><span data-stu-id="41683-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="41683-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="41683-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="41683-104">Konfiguriert, wie der Debugger speicherinterne Aktualisierungen von Metadaten innerhalb des Zielprozesses behandelt.</span><span class="sxs-lookup"><span data-stu-id="41683-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41683-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="41683-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41683-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="41683-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="41683-107">Ein [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) -Enumerationswert, der angibt, ob Speicher interne Aktualisierungen von Metadaten im Ziel Prozess `WriteableMetadataUpdateMode::AlwaysShowUpdates` für den Debugger sichtbar () oder nicht sichtbar ( `WriteableMetadataUpdateMode::LegacyCompatPolicy` ) sind.</span><span class="sxs-lookup"><span data-stu-id="41683-107">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41683-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41683-108">Remarks</span></span>  
 <span data-ttu-id="41683-109">Aktualisierungen von Metadaten im Zielprozess können durch Bearbeiten und Fortfahren, einen Profiler oder <xref:System.Reflection.Emit?displayProperty=nameWithType> ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="41683-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41683-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="41683-110">Requirements</span></span>  
 <span data-ttu-id="41683-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41683-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41683-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41683-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41683-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41683-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41683-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41683-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41683-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41683-115">See also</span></span>

- [<span data-ttu-id="41683-116">ICorDebugProcess7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41683-116">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="41683-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41683-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
