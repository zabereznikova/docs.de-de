---
title: HOST_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: 31640ada28af8e35554b91d5931d427fbaa8dcbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721854"
---
# <a name="host_type-enumeration"></a>HOST_TYPE-Enumeration

Enthält Werte, die den Typ des Hosts angeben, von dem eine Anwendung gestartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Starten Sie die Anwendung aus AppLaunch.exe.<br /><br /> Verwenden Sie diesen Wert für teilweise vertrauenswürdige Anwendungen.|  
|`HOST_TYPE_CORFLAG`|Starten Sie die Anwendung direkt. Das heißt, Sie starten die Anwendung aus ihrer eigenen exe-Datei.<br /><br /> Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.|  
|`HOST_TYPE_DEFAULT`|Identisch mit HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Enumerationen](hosting-enumerations.md)
