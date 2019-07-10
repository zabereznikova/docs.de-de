---
title: BucketParameters-Struktur
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96fee259b31938ddec5820bc1b8d72a96b50c8d8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773879"
---
# <a name="bucketparameters-structure"></a>BucketParameters-Struktur
Speichert den Typnamen eines Ereignisses und die Parameter für die aktuelle Ausnahme, die dem Ereignis zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`fInited`|`true`, wenn der Rest dieser Struktur gültig ist. andernfalls `false`.|  
|`pszEventTypeName`|Der Name des Ereignistyps.|  
|`pszParams`|Ein Array von Zeichenfolgen, von denen jede einen Parameter für die aktuelle Ausnahme, die dem Ereignis zugeordnete angibt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
