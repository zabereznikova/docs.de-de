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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987961"
---
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges-Methode
Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cbMetadata`  
 [in] Größe in Bytes für den Deltametadaten.  
  
 `pbMetadata`  
 [in] Der Puffer, der Deltametadaten enthält. Die Adresse des Puffers wird zurückgegeben, aus der [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) Methode.  
  
 Die relativen virtuellen Adressen (RVA) in den Metadaten muss relativ zum Beginn des MSIL-Codes.  
  
 `cbIL`  
 [in] Größe in Bytes, des Deltas MSIL-Code.  
  
 `pbIL`  
 [in] Puffer, den aktualisierten MSIL-Code enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `pbMetadata` Parameter ist in einem speziellen Delta-Metadaten-Format (als Ausgabeparameter von [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` Vorherige Metadaten als Basis verwendet und werden die einzelnen abweichungen in auf der Basis anzuwenden.  
  
 Im Gegensatz dazu die `pbIL[`] Parameter enthält die neue MSIL für die aktualisierte Methode und die vorherige MSIL für diese Methode vollständig ersetzen soll  
  
 Wenn das Delta MSIL und die Metadaten des Debuggers speicherintern erstellt wurden, wird der Debugger ruft `ApplyChanges` um die Änderungen in die common Language Runtime (CLR) zu senden. Die Laufzeit aktualisiert die Tabellen mit Replikationsmetadaten, fügt die neue MSIL in den Prozess und richtet eine just-in-Time (JIT)-Kompilierung der neuen MSIL. Der Debugger sollte aufrufen, wenn die Änderungen angewendet wurden, [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) für die nächsten bearbeitungssitzung vorbereiten. Der Debugger kann dann mit der Prozess fortgesetzt.  
  
 Jedes Mal, wenn der Debugger ruft `ApplyChanges` auf ein Modul, das Deltametadaten enthält, sollten sie auch aufrufen [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) mit den gleichen Deltametadaten für alle seine Kopien, die Metadaten des Moduls mit Ausnahme des Kopiervorgangs wird verwendet, um die Änderungen auszugeben. Wenn eine Kopie der Metadaten aus irgendeinem Grund-mehr-synchronisiert-wird mit die eigentlichen Metadaten, der Debugger stets wegwerfen, kopieren und rufen Sie eine neue Kopie.  
  
 Wenn die `ApplyChanges` Methode fehlschlägt, ist das Debuggen Sitzung befindet sich in einem ungültigen Zustand und muss neu gestartet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
