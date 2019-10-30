---
title: StackOverflowType-Enumeration
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141470"
---
# <a name="stackoverflowtype-enumeration"></a>StackOverflowType-Enumeration
Enthält Werte, die die zugrunde liegende Ursache eines Stapelüberlauf Ereignisses angeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`SO_ClrEngine`|Der Stapelüberlauf wurde von der Ausführungs-Engine verursacht.|  
|`SO_Managed`|Der Stapelüberlauf wurde durch verwalteten Code verursacht.|  
|`SO_Other`|Der Stapelüberlauf wurde durch nicht verwalteten Code verursacht.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Informationen werden an den Host über einen aufzurufenden Befehl der [iaktiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) -Methode übermittelt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
