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
ms.openlocfilehash: cd4e675b4ba50b47146428d204c28cc943c23c69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688002"
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
  
|Schnittstelle|BESCHREIBUNG|  
|---------------|-----------------|  
|[ICorConfiguration-Schnittstelle](icorconfiguration-interface.md)|Stellt Methoden zum Konfigurieren des Common Language Runtime (CLR) bereit.|  
|[ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)|Stellt Methoden bereit, die es dem Host ermöglichen, den Common Language Runtime explizit zu starten und zu unterbinden, Anwendungs Domänen zu erstellen und zu konfigurieren, auf die Standard Domäne zuzugreifen und alle Domänen aufzuzählen, die im Prozess ausgeführt werden.|  
|[IDebuggerInfo-Schnittstelle](idebuggerinfo-interface.md)|Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.|  
|[IGCHost-Schnittstelle](igchost-interface.md)|Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.|  
|IValidator|Stellt Methoden für die Validierung von portablen ausführbaren Images und die ausführliche Berichterstellung zu Validierungs Fehlern bereit.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Co-Klassen](hosting-coclasses.md)
