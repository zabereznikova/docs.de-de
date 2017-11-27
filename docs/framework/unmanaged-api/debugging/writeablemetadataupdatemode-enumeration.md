---
title: WriteableMetadataUpdateMode-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: WriteableMetadataUpdateMode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 001d80a2232f5b6fbfb43b9de5deafb3317e426d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Verwaltet Kompatibilität mit vorherigen Versionen von .NET Framework, wenn speicherinterne Aktualisierungen von Metadaten sichtbar gemacht werden. Weitere Informationen finden Sie im Abschnitt Hinweise.|  
|`AlwaysShowUpdates`|Macht speicherinterne Aktualisierungen von Metadaten für den Debugger sichtbar.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Mitglied der `WriteableMetadataUpdateMode` Enumeration übergeben werden kann, um die [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) Methode zu steuern, ob in-Memory-Metadaten im Zielprozess updates für den Debugger sichtbar sind.  
  
 Die `LegacyCompatPolicy`-Option erzwingt das gleiche Verhalten wie in den Vorgängerversionen von .NET Framework 4.5.2. Dies bedeutet meist, dass Metadaten von Aktualisierungen nicht sichtbar sind. Es werden jedoch mehrere Debugmethoden aufgerufen, die den Debugger implizit zwingen, Aktualisierungen sichtbar zu machen. Angenommen, wenn der Debugger erfolgreich [ICorDebugILFrame:: GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) den Index einer Variablen nicht im ursprünglichen Metadaten der die Methode, alle Metadaten gefunden, für das Modul mit einer übereinstimmenden den aktuellen Status der Momentaufnahme aktualisiert wird die Prozess. Anders ausgedrückt: Mit der `LegacyCompatPolicy`-Option kann der Debugger möglicherweise keine, nur einen Teil der oder die gesamten Aktualisierungen von Metadaten erkennen. Dies hängt davon ab, wie er andere Teile der nicht verwalteten Debug-API verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [SetWriteableMetadataUpdateMode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
