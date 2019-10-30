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
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136520"
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
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscorwert. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [LockClrVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
