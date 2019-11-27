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
ms.openlocfilehash: 92e40dbe8892d48dba1c54d9cd16faa409440b24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438115"
---
# <a name="notify_filter-enumeration"></a>NOTIFY_FILTER-Enumeration
Identifiziert Rückrufe für Debugger-Funktionen. Weitere Informationen finden Sie unter der [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) -Methode.  
  
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
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Gibt an, dass die [INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) -Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Gibt an, dass die [INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) -Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Gibt an, dass die [INotifySink2:: OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) -Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Gibt an, dass die [INotifySink2:: OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) -Methode aufgerufen werden soll.|  
|`NOTIFY_FILTER_ALLSYNC`|Gibt an, dass alle [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) -Methoden aufgerufen werden sollen.|  
|`NOTIFY_FILTER_ALL`|Aktiviert alle vorhandenen und zukünftigen Benachrichtigungen.|  
|`NOTIFY_FILTER_NONE`|Gibt an, dass keine Benachrichtigungs Methoden aufgerufen werden sollen.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
