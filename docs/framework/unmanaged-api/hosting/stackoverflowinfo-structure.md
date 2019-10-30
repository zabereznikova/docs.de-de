---
title: StackOverflowInfo-Struktur
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105918"
---
# <a name="stackoverflowinfo-structure"></a>StackOverflowInfo-Struktur
Speichert den Typ des aufgetretenen Überlaufs und Informationen zu der Ausnahme, die aufgrund des Überlaufs ausgelöst wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`soType`|Ein Wert der [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) -Enumeration, der den Typ des Überlaufs angibt.|  
|`pExceptionInfo`|Ein Zeiger auf ein Win32-`EXCEPTION_POINTERS` Objekt, das einen Ausnahme Daten Satz mit einer Computer unabhängigen Beschreibung einer Ausnahme und einen Kontext Daten Satz mit einer Computer abhängigen Beschreibung des Prozessor Kontexts zum Zeitpunkt der Ausnahme enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `StackOverflowInfo`-Objekt wird für `Event_StackOverflow` Ereignisse an die [iaktiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) -Methode weitergegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
