---
title: ValidatorFlags-Enumeration
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa10ae1cf67339a6719210f3162f19ac648e8ee5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127412"
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags-Enumeration
Enthält Werte, die den Typ der Überprüfung angeben, die in einem Aufruf ausgeführt werden, sollte die [ICLRValidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|Gibt an, dass nur die Microsoft intermediate Language (MSIL) in der ausführbaren Datei überprüft werden sollen.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Gibt an, dass nur das Format der ausführbaren Datei überprüft werden sollen.|  
|`VALIDATOR_EXTRA_VERBOSE`|Gibt an, dass alle Typen der Überprüfung ausgeführt und auf gemeldet werden soll.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Gibt an, dass das Format der ausführbaren Datei nicht überprüft werden soll.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Gibt an, dass Meldungen für Validierungsfehler auf die Zeilen des Quellcodes enthalten soll, die Validierungsfehler auslösen. Der Wert dieses Felds ist ungültig in .NET Framework, Version 2.0.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
