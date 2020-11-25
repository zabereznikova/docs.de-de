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
ms.openlocfilehash: 90220c2bfea683ff0472473e180c9e11ea568672
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720034"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)
- [INotifySource2-Schnittstelle](inotifysource2-interface.md)
- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [RegisterNotifySource-Methode](inotifyconnection2-registernotifysource-method.md)
