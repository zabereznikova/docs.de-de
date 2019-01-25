---
title: ESymbolReadingPolicy-Enumeration
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e17f88cf7f0d8572e65d00d8500a1fd83aa44eeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663913"
---
# <a name="esymbolreadingpolicy-enumeration"></a>ESymbolReadingPolicy-Enumeration
Enthält Werte, die die Richtlinie für das Lesen von Programmdatenbankdateien (PDB) festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Gibt an, dass der Debugger die PDB-Dateien immer lesen soll.|  
|`eSymbolReadingFullTrustOnly`|Gibt an, dass der Debugger nur PDB-Dateien gelesen werden soll, die mit vollständig vertrauenswürdigen Assemblys verknüpft sind.|  
|`eSymbolReadingNever`|Gibt an, dass der Debugger keine PDB-Dateien lesen soll.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ESymbolReadingPolicy` Enumeration wird zusammen mit den [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
