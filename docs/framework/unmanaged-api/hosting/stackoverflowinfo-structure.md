---
title: StackOverflowInfo-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackOverflowInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: StackOverflowInfo
helpviewer_keywords: StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 102f744ecc769a10161cd20767e8e49c838252a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="stackoverflowinfo-structure"></a>StackOverflowInfo-Struktur
Speichert den Typ des aufgetretenen Überlaufs und Informationen für die Ausnahme, die aufgrund eines Überlaufs in der ausgelöst wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`soType`|Der Wert der [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) -Enumeration, der den Typ des Überlaufs angibt.|  
|`pExceptionInfo`|Ein Zeiger auf eine Win32- `EXCEPTION_POINTERS` Objekt, das einen Ausnahmedatensatz mit eine computerunabhängige Beschreibung einer Ausnahme und einen Kontextdatensatz mit einer Beschreibung rechnerabhängige des Kontexts Prozessor zum Zeitpunkt der Ausnahme enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `StackOverflowInfo` Objekt wird zum Übergeben der [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) Methode zum `Event_StackOverflow` Ereignisse.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
