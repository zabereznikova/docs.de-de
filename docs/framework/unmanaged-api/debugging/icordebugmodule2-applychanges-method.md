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
ms.openlocfilehash: 99824e9a7fd759fb30bfa377156fc28eb934a2b4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212216"
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
 in Puffer, der die Delta Metadaten enthält. Die Adresse des Puffers wird von der [IMetaDataEmit2:: SaveDelta](../metadata/imetadataemit2-savedeltatomemory-method.md) -Methode zurückgegeben.  
  
 Die relativen virtuellen Adressen (RVAs) in den Metadaten sollten relativ zum Beginn des MSIL-Codes sein.  
  
 `cbIL`  
 in Größe (in Bytes) des Delta-MSIL-Codes.  
  
 `pbIL`  
 in Puffer, der den aktualisierten MSIL-Code enthält.  
  
## <a name="remarks"></a>Hinweise  
 Der- `pbMetadata` Parameter befindet sich in einem speziellen Delta-Metadatenformat (als Output by [IMetaDataEmit2:: SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata`nimmt vorherige Metadaten als Basis an und beschreibt individuelle Änderungen, die auf diese Basis angewendet werden sollen.  
  
 Im Gegensatz dazu `pbIL[` enthält der Parameter "]" die neue MSIL für die aktualisierte Methode und soll die vorherige MSIL für diese Methode vollständig ersetzen.  
  
 Wenn die Delta-MSIL und die Metadaten im Speicher des Debuggers erstellt wurden, ruft der Debugger `ApplyChanges` auf, um die Änderungen an die Common Language Runtime (CLR) zu senden. Die Laufzeit aktualisiert die Metadatentabellen, platziert die neue MSIL in den Prozess und richtet eine JIT-Kompilierung (Just-in-Time) der neuen MSIL ein. Wenn die Änderungen angewendet wurden, sollte der Debugger [IMetaDataEmit2:: retartenclog](../metadata/imetadataemit2-resetenclog-method.md) zum Vorbereiten der nächsten Bearbeitungs Sitzung aufruft. Der Debugger kann den Vorgang dann fortsetzen.  
  
 Immer wenn der Debugger `ApplyChanges` für ein Modul aufruft, das über Delta Metadaten verfügt, sollte es auch [IMetaDataEmit:: ApplyEditAndContinue](../metadata/imetadataemit-applyeditandcontinue-method.md) mit denselben Delta Metadaten für alle Kopien der Metadaten dieses Moduls aufrufen, mit Ausnahme der zum Ausgeben der Änderungen verwendeten Kopie. Wenn eine Kopie der Metadaten irgendwie nicht mehr mit den eigentlichen Metadaten synchronisiert wird, kann der Debugger diese Kopie immer verwerfen und eine neue Kopie erhalten.  
  
 Wenn die `ApplyChanges` Methode fehlschlägt, befindet sich die Debugsitzung in einem ungültigen Zustand und muss neu gestartet werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
