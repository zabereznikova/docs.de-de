---
title: NOTIFY_FILTER-Enumeration
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09c36dd65c8a4202f13d362668f74cd9a362e35a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744358"
---
# <a name="notifyfilter-enumeration"></a>NOTIFY_FILTER-Enumeration
Identifiziert die Rückrufe für Debugger-Funktionen. Weitere Informationen finden Sie unter den [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Gibt an, dass die [INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Gibt an, dass die [INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Gibt an, dass die [INotifySink2:: OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Gibt an, dass die [INotifySink2:: OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ALLSYNC`|Gibt an, dass alle der [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) Methoden aufgerufen werden soll.|  
|`NOTIFY_FILTER_ALL`|Aktiviert alle vorhandene und künftige Benachrichtigungen an.|  
|`NOTIFY_FILTER_NONE`|Gibt an, dass keine Benachrichtigungsmethoden aufgerufen werden soll.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
