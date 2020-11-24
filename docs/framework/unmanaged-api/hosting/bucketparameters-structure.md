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
ms.openlocfilehash: 8b54cb30ec96ad0fb7851af6f2d465fe771886ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677853"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`fInited`|`true`, wenn der Rest dieser-Struktur gültig ist. andernfalls `false` .|  
|`pszEventTypeName`|Der Name des Ereignis Typs.|  
|`pszParams`|Ein Array von Zeichen folgen, von denen jede einen Parameter für die aktuelle Ausnahme angibt, die dem Ereignis zugeordnet ist.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](hosting-structures.md)
