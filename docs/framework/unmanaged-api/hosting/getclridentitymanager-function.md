---
title: GetCLRIdentityManager-Funktion
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 9d1196749e033c71b0c8923d0325eb4886122d1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733658"
---
# <a name="getclridentitymanager-function"></a>GetCLRIdentityManager-Funktion

Ruft einen Zeiger auf eine-Schnittstelle ab, die dem Common Language Runtime (CLR) das Verwalten von Identitäten ermöglicht.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `riid`  
 in Ein `REFIID` (ein Schnittstellen Bezeichner), der angibt, welche Schnittstelle Sie erhalten. Dieser Wert muss entweder IID_ICLRAssemblyIdentityManager oder IID_ICLRHostBindingPolicyManager sein.  
  
 `ppManager`  
 vorgenommen Ein Zeiger auf die Adresse eines [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) -Objekts oder eines [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) -Objekts.  
  
## <a name="remarks"></a>Hinweise  

 Aufrufen der [GetRealProcAddress](getrealprocaddress-function.md) -Funktion, um einen Zeiger auf die Funktion zu erhalten `GetCLRIdentityManager` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorWks.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
