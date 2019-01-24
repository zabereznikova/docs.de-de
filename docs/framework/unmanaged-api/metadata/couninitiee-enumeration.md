---
title: COUNINITIEE-Enumeration
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 475ae98d2bf7ea5132c9ec4555070f8bb2999cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744010"
---
# <a name="couninitiee-enumeration"></a>COUNINITIEE-Enumeration
Gibt Konstanten an, die von verwendet [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) beim Initialisieren der common Language Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|Gibt die Initialisierung der Standardmodus an.|  
|`COUNINITEE_DLL`|Gibt die Initialisierung im Modus für das Entladen einer Assemblys an.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
