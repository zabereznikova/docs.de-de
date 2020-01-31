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
ms.openlocfilehash: 5c3f2f7a9c0804b71c9c8a52bb032aca7c03825e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790289"
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
  
|Mitgliedsname|Beschreibung|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Verwaltet Kompatibilität mit vorherigen Versionen von .NET Framework, wenn speicherinterne Aktualisierungen von Metadaten sichtbar gemacht werden. Weitere Informationen finden Sie im Abschnitt Hinweise.|  
|`AlwaysShowUpdates`|Macht speicherinterne Aktualisierungen von Metadaten für den Debugger sichtbar.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Member der `WriteableMetadataUpdateMode`-Enumeration kann an die [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) -Methode übermittelt werden, um zu steuern, ob Speicher interne Aktualisierungen von Metadaten im Ziel Prozess für den Debugger sichtbar sind.  
  
 Die `LegacyCompatPolicy`-Option erzwingt das gleiche Verhalten wie in den Vorgängerversionen von .NET Framework 4.5.2. Dies bedeutet meist, dass Metadaten von Aktualisierungen nicht sichtbar sind. Es werden jedoch mehrere Debugmethoden aufgerufen, die den Debugger implizit zwingen, Aktualisierungen sichtbar zu machen. Wenn der Debugger z. b. [ICorDebugILFrame:: GetLocalVariable](icordebugilframe-getlocalvariable-method.md) an den Index einer Variablen übergibt, die in den ursprünglichen Metadaten der Methode nicht gefunden wurde, werden alle Metadaten für das Modul auf eine Momentaufnahme aktualisiert, die dem aktuellen Status des Prozesses entspricht. Anders ausgedrückt: Mit der `LegacyCompatPolicy`-Option kann der Debugger möglicherweise keine, nur einen Teil der oder die gesamten Aktualisierungen von Metadaten erkennen. Dies hängt davon ab, wie er andere Teile der nicht verwalteten Debug-API verwendet.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](debugging-enumerations.md)
- [SetWriteableMetadataUpdateMode-Methode](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
