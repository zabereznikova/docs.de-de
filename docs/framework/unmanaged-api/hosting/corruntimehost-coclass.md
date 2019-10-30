---
title: CorRuntimeHost-Co-Klasse
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: 512009e053605e2018f1fcbafa422c1a36ddecc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136905"
---
# <a name="corruntimehost-coclass"></a>CorRuntimeHost-Co-Klasse
Stellt Schnittstellen für die Verwaltung von Anwendungen bereit, die von der Common Language Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|[ICorConfiguration-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Stellt Methoden zum Konfigurieren des Common Language Runtime (CLR) bereit.|  
|[ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Stellt Methoden bereit, die es dem Host ermöglichen, den Common Language Runtime explizit zu starten und zu unterbinden, Anwendungs Domänen zu erstellen und zu konfigurieren, auf die Standard Domäne zuzugreifen und alle Domänen aufzuzählen, die im Prozess ausgeführt werden.|  
|[IDebuggerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.|  
|[IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.|  
|IValidator|Stellt Methoden für die Validierung von portablen ausführbaren Images und die ausführliche Berichterstellung zu Validierungs Fehlern bereit.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
