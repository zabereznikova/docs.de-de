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
ms.openlocfilehash: c324019e1e62701f4f2aaba1c00948b292ba6847
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127910"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="0c406-102">ICorDebugModule2::ApplyChanges-Methode</span><span class="sxs-lookup"><span data-stu-id="0c406-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="0c406-103">Wendet die Änderungen an den Metadaten und den Änderungen im MSIL-Code (Microsoft Intermediate Language) auf den laufenden Prozess an.</span><span class="sxs-lookup"><span data-stu-id="0c406-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c406-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c406-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c406-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c406-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="0c406-106">in Größe (in Bytes) der Delta Metadaten.</span><span class="sxs-lookup"><span data-stu-id="0c406-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="0c406-107">in Puffer, der die Delta Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="0c406-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="0c406-108">Die Adresse des Puffers wird von der [IMetaDataEmit2:: SaveDelta](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0c406-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="0c406-109">Die relativen virtuellen Adressen (RVAs) in den Metadaten sollten relativ zum Beginn des MSIL-Codes sein.</span><span class="sxs-lookup"><span data-stu-id="0c406-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="0c406-110">in Größe (in Bytes) des Delta-MSIL-Codes.</span><span class="sxs-lookup"><span data-stu-id="0c406-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="0c406-111">in Puffer, der den aktualisierten MSIL-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="0c406-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c406-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c406-112">Remarks</span></span>  
 <span data-ttu-id="0c406-113">Der `pbMetadata`-Parameter befindet sich in einem speziellen Delta-Metadatenformat (als Output by [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="0c406-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="0c406-114">`pbMetadata` nimmt vorherige Metadaten als Basis an und beschreibt individuelle Änderungen, die auf diese Basis angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0c406-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="0c406-115">Im Gegensatz dazu enthält der Parameter "`pbIL[`]" die neue MSIL für die aktualisierte Methode und soll die vorherige MSIL für diese Methode vollständig ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0c406-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="0c406-116">Wenn die Delta-MSIL und die Metadaten im Speicher des Debuggers erstellt wurden, ruft der Debugger `ApplyChanges` auf, um die Änderungen an die Common Language Runtime (CLR) zu senden.</span><span class="sxs-lookup"><span data-stu-id="0c406-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="0c406-117">Die Laufzeit aktualisiert die Metadatentabellen, platziert die neue MSIL in den Prozess und richtet eine JIT-Kompilierung (Just-in-Time) der neuen MSIL ein.</span><span class="sxs-lookup"><span data-stu-id="0c406-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="0c406-118">Wenn die Änderungen angewendet wurden, sollte der Debugger [IMetaDataEmit2:: retartenclog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) zum Vorbereiten der nächsten Bearbeitungs Sitzung aufruft.</span><span class="sxs-lookup"><span data-stu-id="0c406-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="0c406-119">Der Debugger kann den Vorgang dann fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="0c406-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="0c406-120">Immer wenn der Debugger `ApplyChanges` in einem Modul aufruft, das über Delta Metadaten verfügt, sollte es auch [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) mit denselben Delta Metadaten für alle Kopien der Metadaten dieses Moduls aufrufen, mit Ausnahme der zum Ausgeben der Änderungen verwendeten Kopie.</span><span class="sxs-lookup"><span data-stu-id="0c406-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="0c406-121">Wenn eine Kopie der Metadaten irgendwie nicht mehr mit den eigentlichen Metadaten synchronisiert wird, kann der Debugger diese Kopie immer verwerfen und eine neue Kopie erhalten.</span><span class="sxs-lookup"><span data-stu-id="0c406-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="0c406-122">Wenn die `ApplyChanges`-Methode fehlschlägt, befindet sich die Debugsitzung in einem ungültigen Zustand und muss neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c406-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c406-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c406-123">Requirements</span></span>  
 <span data-ttu-id="0c406-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c406-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c406-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c406-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c406-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c406-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c406-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c406-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
