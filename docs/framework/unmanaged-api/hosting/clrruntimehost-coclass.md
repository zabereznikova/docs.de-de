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
ms.openlocfilehash: 40766ce5837053493f2e3f1f25fe7d1d63ec695f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616800"
---
# <a name="clrruntimehost-coclass"></a>CLRRuntimeHost-Co-Klasse
Stellt Schnittstellen zum Verwalten der Codeausführung durch die Laufzeit bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Schnittstelle|BESCHREIBUNG|  
|---------------|-----------------|  
|[ICLRRuntimeHost-Schnittstelle](iclrruntimehost-interface.md)|Stellt Methoden zum Steuern der Ausführung von Anwendungen durch die Laufzeit bereit.|  
|[ICLRValidator-Schnittstelle](iclrvalidator-interface.md)|Stellt Methoden für die Validierung von portablen ausführbaren Images sowie für die ausführliche Berichterstellung von Validierungs Fehlern bereit.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosting-Co-Klassen](hosting-coclasses.md)
