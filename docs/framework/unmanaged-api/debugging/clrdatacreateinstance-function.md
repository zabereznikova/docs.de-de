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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d44f9b5dc42147959d3f1d127a64d39258f515
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274262"
---
# <a name="clrdatacreateinstance-function"></a>CLRDataCreateInstance-Funktion
Erstellt ein Schnittstellen Objekt für das angegebene Ziel Element.  
  
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
 in Der Bezeichner der Schnittstelle, die instanziiert werden soll.  
  
 `target`  
 in Ein Zeiger auf ein vom Benutzer implementiertes [ICLRDataTarget](iclrdatatarget-interface.md) -Objekt, das das Ziel Element darstellt, für das das Schnittstellen Objekt erstellt werden soll.  
  
 `iface`  
 vorgenommen Ein Zeiger auf die Adresse des zurückgegebenen Schnittstellen Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Das `ICLRDataTarget` -Objekt wird vom Writer der debugginganwendung implementiert. Die-Implementierung hängt vom Typ des dargestellten Ziel Elements ab. Das Ziel Element kann ein Prozess, ein Speicher Abbild, ein Remote Computer usw. sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** ClrData.idl  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)
