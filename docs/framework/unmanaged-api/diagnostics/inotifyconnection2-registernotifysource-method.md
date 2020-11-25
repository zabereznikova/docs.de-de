---
title: INotifyConnection2::RegisterNotifySource-Methode
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: 1286dd970e437af0a8b607ed050ab4838f73a41f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720047"
---
# <a name="inotifyconnection2registernotifysource-method"></a>INotifyConnection2::RegisterNotifySource-Methode

Installiert eine angegebene Benachrichtigungs Quelle.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `in_pNotifySource`  
 in Gibt das-Objekt an, das als Benachrichtigungs Quelle verwendet werden soll.  
  
 `out_ppNotifySink`  
 vorgenommen Empfängt das-Objekt, das als Benachrichtigungs Senke verwendet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)
- [INotifySource2-Schnittstelle](inotifysource2-interface.md)
- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [UnregisterNotifySource-Methode](inotifyconnection2-unregisternotifysource-method.md)
