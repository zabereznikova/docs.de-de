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
ms.openlocfilehash: 941093b9a0856c2b716ba359c854473f3c9ea26a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006518"
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
|`soType`|Ein Wert der [StackOverflowType](stackoverflowtype-enumeration.md) -Enumeration, der den Typ des Überlaufs angibt.|  
|`pExceptionInfo`|Ein Zeiger auf ein Win32 `EXCEPTION_POINTERS` -Objekt, das einen Ausnahme Daten Satz mit einer Computer unabhängigen Beschreibung einer Ausnahme und einem Kontext Daten Satz mit einer vom Computer abhängigen Beschreibung des Prozessor Kontexts zum Zeitpunkt der Ausnahme enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Ein- `StackOverflowInfo` Objekt wird für-Ereignisse an die [iaktiononclrevent:: OnEvent](iactiononclrevent-onevent-method.md) -Methode weitergegeben `Event_StackOverflow` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](hosting-structures.md)
