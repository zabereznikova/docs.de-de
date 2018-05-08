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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fce759877ad5e3c9041344647781da07ad19a45a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hosttype-enumeration"></a>HOST_TYPE-Enumeration
Enthält Werte, die den Typ des Hosts angeben, die eine Anwendung startet.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Starten Sie die Anwendung über AppLaunch.exe.<br /><br /> Verwenden Sie diesen Wert für teilweise vertrauenswürdige Anwendungen.|  
|`HOST_TYPE_CORFLAG`|Starten Sie die Anwendung direkt. D. h., starten Sie die Anwendung aus einer eigenen .exe-Datei.<br /><br /> Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.|  
|`HOST_TYPE_DEFAULT`|Identisch mit HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
