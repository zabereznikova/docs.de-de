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
ms.openlocfilehash: 57f771d933e896677dfc0bd5d9dac58da2af22c8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617255"
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
 vorgenommen Ein Zeiger auf die Adresse eines [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) -Objekts oder eines [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) -Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen der [GetRealProcAddress](getrealprocaddress-function.md) -Funktion, um einen Zeiger auf die Funktion zu erhalten `GetCLRIdentityManager` .  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscorwert. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
