---
title: _EFN_GetManagedObjectFieldInfo-Funktion
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e7d031d4a4f4e67134f4b88f3e3ff47316ce3b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183143"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a>_EFN_GetManagedObjectFieldInfo-Funktion
Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `Client`  
 [in] Ein Zeiger auf den Client Debuggen.  
  
 `objAddr`  
 [in] Ein Zeiger des verwalteten Objekts.  
  
 szFieldName  
 [in] Ein verwaltetes Objektzeiger auf den Namen des Felds.  
  
 `pValue`  
 [out] Der Wert des Felds. Dieser Parameter kann NULL sein.  
  
 `pOffset`  
 [out] Der Offset vom `objAddr` auf das Feld. Dieser Parameter kann NULL sein.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Offset 0 ist, wird kein Offset geschrieben.  
  
 Es ist kein verwalteter Code für den Thread aktuell im Kontext, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einer Funktion 0xa0 und Fehlercode 0 x 1000 zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace.h  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
