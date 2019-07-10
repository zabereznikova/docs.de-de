---
title: COINITIEE-Enumeration
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f5a2b6b0970f3cb64ee339e6a1a409354a60e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780951"
---
# <a name="coinitiee-enumeration"></a>COINITIEE-Enumeration
Gibt Konstanten an, die von verwendet [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) beim Initialisieren der common Language Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Initialisierung-Standardmodus. Initialisiert die Laufzeit und erstellt die <xref:System.AppDomain>.|  
|`COINITEE_DLL`|Führen Sie eine verwaltete DLL initialisiert.|  
|`COINITEE_MAIN`|Führen Sie eine verwaltete EXE-Datei initialisiert. Dies initialisiert die Laufzeit jedoch nicht die Standardeinstellung erstellt <xref:System.AppDomain>, das nach dem Eingeben der Hauptroutine der EXE-Datei erstellt wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
