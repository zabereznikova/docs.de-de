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
ms.openlocfilehash: 5a406e945a67352bc7f126b40bd56f4a11dd693b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419542"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="44453-102">ICorDebugModule2::ApplyChanges-Methode</span><span class="sxs-lookup"><span data-stu-id="44453-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="44453-103">Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.</span><span class="sxs-lookup"><span data-stu-id="44453-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44453-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44453-104">Syntax</span></span>  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44453-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44453-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="44453-106">[in] Größe in Bytes, der die Deltametadaten.</span><span class="sxs-lookup"><span data-stu-id="44453-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="44453-107">[in] Der Puffer, der Deltametadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="44453-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="44453-108">Die Adresse des Puffers wird zurückgegeben, aus der [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="44453-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="44453-109">Der relativen virtuellen Adresse (RVA) in den Metadaten sollten relativ zum Beginn des MSIL-Codes sein.</span><span class="sxs-lookup"><span data-stu-id="44453-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="44453-110">[in] Größe in Bytes, der das Delta-MSIL-Code.</span><span class="sxs-lookup"><span data-stu-id="44453-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="44453-111">[in] Puffer, den aktualisierte MSIL-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="44453-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44453-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44453-112">Remarks</span></span>  
 <span data-ttu-id="44453-113">Die `pbMetadata` Parameter ist in einem speziellen Delta-Metadaten-Format (als Ausgabeparameter von [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="44453-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="44453-114">`pbMetadata` vorherigen Metadaten als Basis verwendet, und einzelne Änderungen auf der Basis anwenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44453-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="44453-115">Im Gegensatz dazu die `pbIL[`]-Parameter enthält die neue MSIL für die aktualisierte Methode und die vorherige MSIL für diese Methode vollständig ersetzen sollen</span><span class="sxs-lookup"><span data-stu-id="44453-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="44453-116">Wenn das Delta MSIL und Metadaten in der Debugger-Speicher erstellt wurde, wird der Debugger ruft `ApplyChanges` um die Änderungen in die common Language Runtime (CLR) zu senden.</span><span class="sxs-lookup"><span data-stu-id="44453-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="44453-117">Die Common Language Runtime aktualisiert ihre Metadatentabellen, fügt die neue MSIL in den Prozess und eine just-in-Time (JIT)-Kompilierung der neuen MSIL richtet.</span><span class="sxs-lookup"><span data-stu-id="44453-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="44453-118">Wenn die Änderungen angewendet wurden, sollte der Debugger Aufrufen [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) in Vorbereitung auf die nächste bearbeitungssitzung.</span><span class="sxs-lookup"><span data-stu-id="44453-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="44453-119">Der Debugger kann dann mit der Prozess fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="44453-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="44453-120">Wenn der Debugger ruft `ApplyChanges` auf ein Modul, das Deltametadaten aufweist, sollten sie auch aufrufen [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) mit den gleichen Deltametadaten für alle seine Kopien der Metadaten des Moduls, mit Ausnahme der Kopie wird verwendet, um die Änderungen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="44453-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="44453-121">Wenn Sie eine Kopie der Metadaten-mehr-synchronisiert-wird mit den tatsächlichen Metadaten der Debugger kann immer verwerfen diese Kopie und rufen Sie eine neue Kopie.</span><span class="sxs-lookup"><span data-stu-id="44453-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="44453-122">Wenn die `ApplyChanges` Methode fehlschlägt, durch die Debugversionen Sitzung befindet sich in einem ungültigen Zustand und muss neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="44453-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44453-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44453-123">Requirements</span></span>  
 <span data-ttu-id="44453-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44453-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44453-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44453-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44453-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44453-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44453-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44453-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
