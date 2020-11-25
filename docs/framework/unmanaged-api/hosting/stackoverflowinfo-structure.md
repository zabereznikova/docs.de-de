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
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729927"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`soType`|Ein Wert der [StackOverflowType](stackoverflowtype-enumeration.md) -Enumeration, der den Typ des Überlaufs angibt.|  
|`pExceptionInfo`|Ein Zeiger auf ein Win32 `EXCEPTION_POINTERS` -Objekt, das einen Ausnahme Daten Satz mit einer Computer unabhängigen Beschreibung einer Ausnahme und einem Kontext Daten Satz mit einer vom Computer abhängigen Beschreibung des Prozessor Kontexts zum Zeitpunkt der Ausnahme enthält.|  
  
## <a name="remarks"></a>Hinweise  

 Ein- `StackOverflowInfo` Objekt wird für-Ereignisse an die [iaktiononclrevent:: OnEvent](iactiononclrevent-onevent-method.md) -Methode weitergegeben `Event_StackOverflow` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](hosting-structures.md)
