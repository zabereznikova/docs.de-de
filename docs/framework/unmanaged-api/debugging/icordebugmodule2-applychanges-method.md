---
title: ICorDebugModule2::ApplyChanges-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab0e28bd21b66f370a1a1e82359fe474574fd7bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481575"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="28778-102">ICorDebugModule2::ApplyChanges-Methode</span><span class="sxs-lookup"><span data-stu-id="28778-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="28778-103">Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.</span><span class="sxs-lookup"><span data-stu-id="28778-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28778-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28778-104">Syntax</span></span>  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28778-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28778-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="28778-106">[in] Größe in Bytes für den Deltametadaten.</span><span class="sxs-lookup"><span data-stu-id="28778-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="28778-107">[in] Der Puffer, der Deltametadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="28778-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="28778-108">Die Adresse des Puffers wird zurückgegeben, aus der [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="28778-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="28778-109">Die relativen virtuellen Adressen (RVA) in den Metadaten muss relativ zum Beginn des MSIL-Codes.</span><span class="sxs-lookup"><span data-stu-id="28778-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="28778-110">[in] Größe in Bytes, des Deltas MSIL-Code.</span><span class="sxs-lookup"><span data-stu-id="28778-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="28778-111">[in] Puffer, den aktualisierten MSIL-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="28778-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28778-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28778-112">Remarks</span></span>  
 <span data-ttu-id="28778-113">Die `pbMetadata` Parameter ist in einem speziellen Delta-Metadaten-Format (als Ausgabeparameter von [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="28778-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="28778-114">`pbMetadata` Vorherige Metadaten als Basis verwendet und werden die einzelnen abweichungen in auf der Basis anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="28778-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="28778-115">Im Gegensatz dazu die `pbIL[`] Parameter enthält die neue MSIL für die aktualisierte Methode und die vorherige MSIL für diese Methode vollständig ersetzen soll</span><span class="sxs-lookup"><span data-stu-id="28778-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="28778-116">Wenn das Delta MSIL und die Metadaten des Debuggers speicherintern erstellt wurden, wird der Debugger ruft `ApplyChanges` um die Änderungen in die common Language Runtime (CLR) zu senden.</span><span class="sxs-lookup"><span data-stu-id="28778-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="28778-117">Die Laufzeit aktualisiert die Tabellen mit Replikationsmetadaten, fügt die neue MSIL in den Prozess und richtet eine just-in-Time (JIT)-Kompilierung der neuen MSIL.</span><span class="sxs-lookup"><span data-stu-id="28778-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="28778-118">Der Debugger sollte aufrufen, wenn die Änderungen angewendet wurden, [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) für die nächsten bearbeitungssitzung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="28778-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="28778-119">Der Debugger kann dann mit der Prozess fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="28778-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="28778-120">Jedes Mal, wenn der Debugger ruft `ApplyChanges` auf ein Modul, das Deltametadaten enthält, sollten sie auch aufrufen [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) mit den gleichen Deltametadaten für alle seine Kopien, die Metadaten des Moduls mit Ausnahme des Kopiervorgangs wird verwendet, um die Änderungen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="28778-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="28778-121">Wenn eine Kopie der Metadaten aus irgendeinem Grund-mehr-synchronisiert-wird mit die eigentlichen Metadaten, der Debugger stets wegwerfen, kopieren und rufen Sie eine neue Kopie.</span><span class="sxs-lookup"><span data-stu-id="28778-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="28778-122">Wenn die `ApplyChanges` Methode fehlschlägt, ist das Debuggen Sitzung befindet sich in einem ungültigen Zustand und muss neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="28778-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28778-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28778-123">Requirements</span></span>  
 <span data-ttu-id="28778-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28778-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28778-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28778-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28778-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28778-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28778-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28778-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
