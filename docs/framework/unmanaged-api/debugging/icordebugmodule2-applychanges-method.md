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
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges-Methode
Wendet die Änderungen an den Metadaten und den Änderungen im MSIL-Code (Microsoft Intermediate Language) auf den laufenden Prozess an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cbMetadata`  
 in Größe (in Bytes) der Delta Metadaten.  
  
 `pbMetadata`  
 in Puffer, der die Delta Metadaten enthält. Die Adresse des Puffers wird von der [IMetaDataEmit2:: SaveDelta](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) -Methode zurückgegeben.  
  
 Die relativen virtuellen Adressen (RVAs) in den Metadaten sollten relativ zum Beginn des MSIL-Codes sein.  
  
 `cbIL`  
 in Größe (in Bytes) des Delta-MSIL-Codes.  
  
 `pbIL`  
 in Puffer, der den aktualisierten MSIL-Code enthält.  
  
## <a name="remarks"></a>Hinweise  
 Der `pbMetadata`-Parameter befindet sich in einem speziellen Delta-Metadatenformat (als Output by [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` nimmt vorherige Metadaten als Basis an und beschreibt individuelle Änderungen, die auf diese Basis angewendet werden sollen.  
  
 Im Gegensatz dazu enthält der Parameter "`pbIL[`]" die neue MSIL für die aktualisierte Methode und soll die vorherige MSIL für diese Methode vollständig ersetzen.  
  
 Wenn die Delta-MSIL und die Metadaten im Speicher des Debuggers erstellt wurden, ruft der Debugger `ApplyChanges` auf, um die Änderungen an die Common Language Runtime (CLR) zu senden. Die Laufzeit aktualisiert die Metadatentabellen, platziert die neue MSIL in den Prozess und richtet eine JIT-Kompilierung (Just-in-Time) der neuen MSIL ein. Wenn die Änderungen angewendet wurden, sollte der Debugger [IMetaDataEmit2:: retartenclog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) zum Vorbereiten der nächsten Bearbeitungs Sitzung aufruft. Der Debugger kann den Vorgang dann fortsetzen.  
  
 Immer wenn der Debugger `ApplyChanges` in einem Modul aufruft, das über Delta Metadaten verfügt, sollte es auch [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) mit denselben Delta Metadaten für alle Kopien der Metadaten dieses Moduls aufrufen, mit Ausnahme der zum Ausgeben der Änderungen verwendeten Kopie. Wenn eine Kopie der Metadaten irgendwie nicht mehr mit den eigentlichen Metadaten synchronisiert wird, kann der Debugger diese Kopie immer verwerfen und eine neue Kopie erhalten.  
  
 Wenn die `ApplyChanges`-Methode fehlschlägt, befindet sich die Debugsitzung in einem ungültigen Zustand und muss neu gestartet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
