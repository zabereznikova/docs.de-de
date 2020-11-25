---
title: INotifySource2::SetNotifyFilter-Methode
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
ms.openlocfilehash: 99bce831405d722f1f1ca0ae56e60f95f2d905e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719930"
---
# <a name="inotifysource2setnotifyfilter-method"></a>INotifySource2::SetNotifyFilter-Methode

Weist einen Benachrichtigungs Filter zur Verwendung mit dieser Quelle zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `in_NotifyFilter`  
 in Eine bitweise Kombination der [NOTIFY_FILTER](notify-filter-enumeration.md) Enumerationswerte, die Rückrufe für die Debugger-API identifizieren.  
  
 `in_pUserThreadFilter`  
 in Ein Zeiger auf eine [USER_THREAD](user-thread-structure.md) -Struktur, die Threads für die Debugger-API identifiziert.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [INotifySource2-Schnittstelle](inotifysource2-interface.md)
- [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)
- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
