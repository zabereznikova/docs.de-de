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
ms.openlocfilehash: b68f24908a5b214d507da8e8a4636a7c55259604
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123015"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a>\_EFN\_getmanagedobjectfieldinfo-Funktion
Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein Zeiger auf den Debugclient.  
  
 `objAddr`  
 in Ein Zeiger für verwaltete Objekte.  
  
 szFieldName  
 in Ein verwalteter Objekt Zeiger auf den Feldnamen.  
  
 `pValue`  
 vorgenommen Der Feldwert. Dieser Parameter kann NULL sein.  
  
 `pOffset`  
 vorgenommen Der Offset von `objAddr` in das Feld. Dieser Parameter kann NULL sein.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Offset 0 (null) ist, wird kein Offset geschrieben.  
  
 Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einem Einrichtungs Wert von 0xa0 und dem Fehlercode 0x1000 zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace. h  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
