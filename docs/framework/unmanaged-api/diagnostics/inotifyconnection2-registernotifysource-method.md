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
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442071"
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Siehe auch

- [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)
- [INotifySource2-Schnittstelle](inotifysource2-interface.md)
- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [UnregisterNotifySource-Methode](inotifyconnection2-unregisternotifysource-method.md)
