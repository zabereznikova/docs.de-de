---
title: ICorRuntimeHost::GetConfiguration-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 2a50814a67be5a01a7413050683a915355665f3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720645"
---
# <a name="icorruntimehostgetconfiguration-method"></a>ICorRuntimeHost::GetConfiguration-Methode

Ruft ein Objekt ab, mit dem der Host die Rückruf Konfiguration des Common Language Runtime (CLR) angeben kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pConfiguration`  
 vorgenommen Ein Zeiger auf die Adresse eines [ICorConfiguration](icorconfiguration-interface.md) -Objekts, das verwendet werden kann, um die CLR zu konfigurieren.  
  
## <a name="remarks"></a>Hinweise  

 Die CLR muss vor der Initialisierung konfiguriert werden. Andernfalls gibt die `GetConfiguration` Methode ein HRESULT zurück, das auf einen Fehler hinweist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:** 1,0, 1,1  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
