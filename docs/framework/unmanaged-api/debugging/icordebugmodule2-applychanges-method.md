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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
  
#### <a name="parameters"></a>Parameter  
 `cbMetadata`  
 [in] Größe in Bytes, der die Deltametadaten.  
  
 `pbMetadata`  
 [in] Der Puffer, der Deltametadaten enthält. Die Adresse des Puffers wird zurückgegeben, aus der [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) Methode.  
  
 Der relativen virtuellen Adresse (RVA) in den Metadaten sollten relativ zum Beginn des MSIL-Codes sein.  
  
 `cbIL`  
 [in] Größe in Bytes, der das Delta-MSIL-Code.  
  
 `pbIL`  
 [in] Puffer, den aktualisierte MSIL-Code enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `pbMetadata` Parameter ist in einem speziellen Delta-Metadaten-Format (als Ausgabeparameter von [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` vorherigen Metadaten als Basis verwendet, und einzelne Änderungen auf der Basis anwenden beschrieben.  
  
 Im Gegensatz dazu die `pbIL[`]-Parameter enthält die neue MSIL für die aktualisierte Methode und die vorherige MSIL für diese Methode vollständig ersetzen sollen  
  
 Wenn das Delta MSIL und Metadaten in der Debugger-Speicher erstellt wurde, wird der Debugger ruft `ApplyChanges` um die Änderungen in die common Language Runtime (CLR) zu senden. Die Common Language Runtime aktualisiert ihre Metadatentabellen, fügt die neue MSIL in den Prozess und eine just-in-Time (JIT)-Kompilierung der neuen MSIL richtet. Wenn die Änderungen angewendet wurden, sollte der Debugger Aufrufen [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) in Vorbereitung auf die nächste bearbeitungssitzung. Der Debugger kann dann mit der Prozess fortgesetzt.  
  
 Wenn der Debugger ruft `ApplyChanges` auf ein Modul, das Deltametadaten aufweist, sollten sie auch aufrufen [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) mit den gleichen Deltametadaten für alle seine Kopien der Metadaten des Moduls, mit Ausnahme der Kopie wird verwendet, um die Änderungen auszugeben. Wenn Sie eine Kopie der Metadaten-mehr-synchronisiert-wird mit den tatsächlichen Metadaten der Debugger kann immer verwerfen diese Kopie und rufen Sie eine neue Kopie.  
  
 Wenn die `ApplyChanges` Methode fehlschlägt, durch die Debugversionen Sitzung befindet sich in einem ungültigen Zustand und muss neu gestartet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
