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
ms.openlocfilehash: dfb1cff3e95c5ff86d22913745b7d14982766b48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175226"
---
# <a name="hosttype-enumeration"></a>HOST_TYPE-Enumeration
Enthält Werte, die den Typ des Hosts angeben, die eine Anwendung ausgeführt werden.  
  
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
|`HOST_TYPE_APPLAUNCH`|Starten Sie die Anwendung über AppLaunch.exe.<br /><br /> Verwenden Sie diesen Wert für teilweise vertrauenswürdigen Anwendungen.|  
|`HOST_TYPE_CORFLAG`|Starten Sie die Anwendung direkt auf. Starten Sie die Anwendung über einen eigenen .exe-Datei, also.<br /><br /> Verwenden Sie diesen Wert für voll vertrauenswürdige Anwendungen.|  
|`HOST_TYPE_DEFAULT`|Same as HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
