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
ms.openlocfilehash: 2ffc575cfcef1089a70ef3b6d38787a5b4c50443
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729823"
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

 Das- `ICLRDataTarget` Objekt wird vom Writer der debugginganwendung implementiert. Die-Implementierung hängt vom Typ des dargestellten Ziel Elements ab. Das Ziel Element kann ein Prozess, ein Speicher Abbild, ein Remote Computer usw. sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)
