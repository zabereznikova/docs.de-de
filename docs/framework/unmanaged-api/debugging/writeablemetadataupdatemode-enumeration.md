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
# <a name="writeablemetadataupdatemode-enumeration"></a>WriteableMetadataUpdateMode-Enumeration

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Stellt Werte bereit, die angeben, ob speicherinterne Aktualisierungen von Metadaten für einen Debugger sichtbar sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>Member  
  
|Membername|BESCHREIBUNG|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Verwaltet Kompatibilität mit vorherigen Versionen von .NET Framework, wenn speicherinterne Aktualisierungen von Metadaten sichtbar gemacht werden. Weitere Informationen finden Sie im Abschnitt Hinweise.|  
|`AlwaysShowUpdates`|Macht speicherinterne Aktualisierungen von Metadaten für den Debugger sichtbar.|  
  
## <a name="remarks"></a>Hinweise  

 Ein Member der- `WriteableMetadataUpdateMode` Enumeration kann an die [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) -Methode übermittelt werden, um zu steuern, ob Speicher interne Aktualisierungen von Metadaten im Ziel Prozess für den Debugger sichtbar sind.  
  
 Die `LegacyCompatPolicy`-Option erzwingt das gleiche Verhalten wie in den Vorgängerversionen von .NET Framework 4.5.2. Dies bedeutet meist, dass Metadaten von Aktualisierungen nicht sichtbar sind. Es werden jedoch mehrere Debugmethoden aufgerufen, die den Debugger implizit zwingen, Aktualisierungen sichtbar zu machen. Wenn der Debugger z. b. [ICorDebugILFrame:: GetLocalVariable](icordebugilframe-getlocalvariable-method.md) an den Index einer Variablen übergibt, die in den ursprünglichen Metadaten der Methode nicht gefunden wurde, werden alle Metadaten für das Modul auf eine Momentaufnahme aktualisiert, die dem aktuellen Status des Prozesses entspricht. Anders ausgedrückt: Mit der `LegacyCompatPolicy`-Option kann der Debugger möglicherweise keine, nur einen Teil der oder die gesamten Aktualisierungen von Metadaten erkennen. Dies hängt davon ab, wie er andere Teile der nicht verwalteten Debug-API verwendet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
- [SetWriteableMetadataUpdateMode-Methode](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
