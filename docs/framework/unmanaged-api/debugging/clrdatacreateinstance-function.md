---
title: CLRDataCreateInstance-Funktion
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: c24963a6e56adfb9f763c6521027744db82cc357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179361"
---
# <a name="clrdatacreateinstance-function"></a>CLRDataCreateInstance-Funktion
Erstellt ein Schnittstellenobjekt für das angegebene Zielelement.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `iid`  
 [in] Der Bezeichner der zu instanziierenden Schnittstelle.  
  
 `target`  
 [in] Ein Zeiger auf ein vom Benutzer implementiertes [ICLRDataTarget-Objekt,](iclrdatatarget-interface.md) das das Zielelement darstellt, für das das Schnittstellenobjekt erstellt werden soll.  
  
 `iface`  
 [out] Ein Zeiger auf die Adresse des zurückgegebenen Schnittstellenobjekts.  
  
## <a name="remarks"></a>Bemerkungen  
 Das `ICLRDataTarget` Objekt wird vom Writer der Debuganwendung implementiert. Die Implementierung hängt vom Typ des dargestellten Zielelements ab. Das Zielelement kann ein Prozess, Speicherabbild, Remotecomputer usw. sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** ClrData.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)
