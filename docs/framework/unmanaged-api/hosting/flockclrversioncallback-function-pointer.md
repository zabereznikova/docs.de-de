---
title: FLockClrVersionCallback-Funktionszeiger
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: d18702a1bb15d2cc6c7b8577b91ed011e9bd0c05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733671"
---
# <a name="flockclrversioncallback-function-pointer"></a>FLockClrVersionCallback-Funktionszeiger

Verweist auf eine Funktion, die vom Common Language Runtime (CLR) aufgerufen wird, um anzugeben, dass die Initialisierung entweder gestartet oder abgeschlossen wurde.  
  
 Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a>Hinweise  

 Diese Funktion wird vom Host implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorWks.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [LockClrVersion-Funktion](lockclrversion-function.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
