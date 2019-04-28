---
title: CLRRuntimeHost-Co-Klasse
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789596"
---
# <a name="clrruntimehost-coclass"></a>CLRRuntimeHost-Co-Klasse
Stellt Schnittstellen für die Verwaltung der Ausführung von Code von der Laufzeit bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|[ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|Stellt Methoden zum Steuern der Ausführung von Anwendungen von der Laufzeit bereit.|  
|[ICLRValidator-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|Stellt Methoden für die Überprüfung von portierbare ausführbare Images und detaillierte Melden von Validierungsfehlern.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
