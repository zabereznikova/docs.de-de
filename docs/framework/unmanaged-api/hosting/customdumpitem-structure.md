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
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176473"
---
# <a name="customdumpitem-structure"></a>CustomDumpItem-Struktur
Beschreibt ein Element, das einem benutzerdefinierten Dump in der Fehlerberichterstattung hinzugefügt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`itemKind`|Ein [ECustomDumpItemKind-Wert,](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) der die Art des hinzuzufügenden Elements angibt.|  
|`pReserved`|Derzeit nicht verwendet. Alle Elemente, die der Union hinzugefügt werden, dürfen nicht größer als die Zeigergröße sein. Wenn `struct` a erforderlich ist, müssen Sie es separat zuweisen und darauf zeigen.|  
  
## <a name="remarks"></a>Bemerkungen  
 [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen `CustomDumpItem`Parameter vom Typ an.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
