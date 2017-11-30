---
title: ValidatorFlags-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ValidatorFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ValidatorFlags
helpviewer_keywords: ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f283beb79ec47454185800bd772904c3c696c7c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags-Enumeration
Enthält Werte, die den Typ der Überprüfung angeben, die in einem Aufruf ausgeführt werden, sollten die [ICLRValidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) Methode.  
  
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
|`VALIDATOR_NOCHECK_PEFORMAT`|Gibt an, dass das Format der ausführbaren Datei nicht überprüft werden sollen.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Gibt an, dass es sich bei Überprüfungsfehlermeldungen die Quellcodezeilen enthalten soll, die Validierungsfehler auslösen. Der Wert dieses Felds ist ungültig in .NET Framework, Version 2.0.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
