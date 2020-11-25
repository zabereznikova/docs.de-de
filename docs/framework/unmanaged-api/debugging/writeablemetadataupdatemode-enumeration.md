---
title: WriteableMetadataUpdateMode-Enumeration
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: 1553e18da10844da28bbaf84ba76bc5c34ca49b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725299"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="b0567-102">WriteableMetadataUpdateMode-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b0567-102">WriteableMetadataUpdateMode Enumeration</span></span>

<span data-ttu-id="b0567-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b0567-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b0567-104">Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="b0567-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0567-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0567-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="b0567-106">Member</span><span class="sxs-lookup"><span data-stu-id="b0567-106">Members</span></span>  
  
|<span data-ttu-id="b0567-107">Membername</span><span class="sxs-lookup"><span data-stu-id="b0567-107">Member name</span></span>|<span data-ttu-id="b0567-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b0567-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="b0567-109">Verwaltet Kompatibilität mit vorherigen Versionen von .NET Framework, wenn speicherinterne Aktualisierungen von Metadaten sichtbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b0567-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="b0567-110">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="b0567-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="b0567-111">Macht speicherinterne Aktualisierungen von Metadaten für den Debugger sichtbar.</span><span class="sxs-lookup"><span data-stu-id="b0567-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0567-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0567-112">Remarks</span></span>  

 <span data-ttu-id="b0567-113">Ein Member der- `WriteableMetadataUpdateMode` Enumeration kann an die [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) -Methode übermittelt werden, um zu steuern, ob Speicher interne Aktualisierungen von Metadaten im Ziel Prozess für den Debugger sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="b0567-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="b0567-114">Die `LegacyCompatPolicy`-Option erzwingt das gleiche Verhalten wie in den Vorgängerversionen von .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="b0567-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="b0567-115">Dies bedeutet meist, dass Metadaten von Aktualisierungen nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="b0567-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="b0567-116">Es werden jedoch mehrere Debugmethoden aufgerufen, die den Debugger implizit zwingen, Aktualisierungen sichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="b0567-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="b0567-117">Wenn der Debugger z. b. [ICorDebugILFrame:: GetLocalVariable](icordebugilframe-getlocalvariable-method.md) an den Index einer Variablen übergibt, die in den ursprünglichen Metadaten der Methode nicht gefunden wurde, werden alle Metadaten für das Modul auf eine Momentaufnahme aktualisiert, die dem aktuellen Status des Prozesses entspricht.</span><span class="sxs-lookup"><span data-stu-id="b0567-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="b0567-118">Anders ausgedrückt: Mit der `LegacyCompatPolicy`-Option kann der Debugger möglicherweise keine, nur einen Teil der oder die gesamten Aktualisierungen von Metadaten erkennen. Dies hängt davon ab, wie er andere Teile der nicht verwalteten Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0567-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0567-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b0567-119">Requirements</span></span>  

 <span data-ttu-id="b0567-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0567-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0567-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0567-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0567-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0567-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0567-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0567-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0567-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0567-124">See also</span></span>

- [<span data-ttu-id="b0567-125">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="b0567-125">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="b0567-126">SetWriteableMetadataUpdateMode-Methode</span><span class="sxs-lookup"><span data-stu-id="b0567-126">SetWriteableMetadataUpdateMode Method</span></span>](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
