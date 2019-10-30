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
ms.openlocfilehash: 61aafb8dc99bb908fc603945ff6ea74054f812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141423"
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags-Enumeration
Enthält Werte, die den Validierungstyp angeben, der bei einem Rückruf der [ICLRValidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) -Methode ausgeführt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`VALIDATOR_CHECK_ILONLY`|Gibt an, dass nur die Microsoft Intermediate Language (MSIL) in der ausführbaren Datei überprüft werden soll.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Gibt an, dass nur das Format der ausführbaren Datei überprüft werden soll.|  
|`VALIDATOR_EXTRA_VERBOSE`|Gibt an, dass alle Validierungs Typen ausgeführt und gemeldet werden sollen.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Gibt an, dass das Format der ausführbaren Datei nicht überprüft werden soll.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Gibt an, dass Validierungs Fehlermeldungen die Zeilen des Quellcodes einschließen sollen, durch die Validierungs Fehler ausgegeben werden. Dieser Feldwert ist in der .NET Framework-Version 2,0 ungültig.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator. idl, IValidator. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
