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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218562"
---
# <a name="corruntimehost-coclass"></a>CorRuntimeHost-Co-Klasse
Stellt Schnittstellen zum Verwalten von Anwendungen, die von der common Language Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|[ICorConfiguration-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Stellt Methoden für die common Language Runtime (CLR) konfigurieren.|  
|[ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Bietet Methoden, mit denen der Host zum Starten und beenden die common Language Runtime explizit zum Erstellen und Konfigurieren von Anwendungsdomänen, die Zugriff auf die Standarddomäne und zum Aufzählen von allen Domänen, die im Prozess ausgeführt wird.|  
|[IDebuggerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Stellt Methoden zum Abrufen von Informationen über den Status der Debugdienste bereit.|  
|[IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.|  
|"IValidator"|Stellt Methoden für die Überprüfung der portierbare ausführbare Images und ausführliche berichterstellung von Validierungsfehlern.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
