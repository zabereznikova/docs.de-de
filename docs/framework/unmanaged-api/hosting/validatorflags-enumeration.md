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
ms.openlocfilehash: 92c430cdb8b46cf75dde9a8395ce713116dc05a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732855"
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags-Enumeration

Enthält Werte, die den Validierungstyp angeben, der bei einem Rückruf der [ICLRValidator:: Validate](iclrvalidator-validate-method.md) -Methode ausgeführt werden soll.  
  
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|Gibt an, dass nur die Microsoft Intermediate Language (MSIL) in der ausführbaren Datei überprüft werden soll.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Gibt an, dass nur das Format der ausführbaren Datei überprüft werden soll.|  
|`VALIDATOR_EXTRA_VERBOSE`|Gibt an, dass alle Validierungs Typen ausgeführt und gemeldet werden sollen.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Gibt an, dass das Format der ausführbaren Datei nicht überprüft werden soll.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Gibt an, dass Validierungs Fehlermeldungen die Zeilen des Quellcodes einschließen sollen, durch die Validierungs Fehler ausgegeben werden. Dieser Feldwert ist in der .NET Framework-Version 2,0 ungültig.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** IValidator. idl, IValidator. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRErrorReportingManager-Schnittstelle](iclrerrorreportingmanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
