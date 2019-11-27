---
title: INotifyConnection2::UnregisterNotifySource-Methode
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: cf399d0c7dec7528f02988ddfe6ca5c0b1f0c4c3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440987"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>INotifyConnection2::UnregisterNotifySource-Methode
Entfernt ein angegebenes Benachrichtigungs Quell Objekt aus der Verbindung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `in_pNotifySource`  
 in Benachrichtigungs Objekt, deren Registrierung aufgehoben werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Siehe auch

- [INotifyConnection2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [INotifySource2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [INotifySink2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [RegisterNotifySource-Methode](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
