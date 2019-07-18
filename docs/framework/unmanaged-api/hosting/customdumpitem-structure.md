---
title: CustomDumpItem-Struktur
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05f5d3fbe05ad1e97a1ae61ed0496f314c4ec5cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765965"
---
# <a name="customdumpitem-structure"></a>CustomDumpItem-Struktur
Beschreibt ein Element ein benutzerdefiniertes Speicherabbild in der Fehlerberichterstattung hinzugefügt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`itemKind`|Ein [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) Wert, der die Art des hinzuzufügenden Elements angibt.|  
|`pReserved`|Derzeit nicht verwendet. Keine Elemente hinzugefügt, die Union müssen nicht größer als die Größe des Zeigers sein. Wenn eine `struct` ist erforderlich, müssen Sie diese separat zugeordnet werden und darauf verweisen.|  
  
## <a name="remarks"></a>Hinweise  
 [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen Parameter vom Typ `CustomDumpItem`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
