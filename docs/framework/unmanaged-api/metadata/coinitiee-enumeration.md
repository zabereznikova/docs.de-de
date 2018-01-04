---
title: COINITIEE-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COINITIEE
helpviewer_keywords: COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a>COINITIEE-Enumeration
Gibt Konstanten verwendet [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) beim Initialisieren der common Language Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Initialisierung-Standardmodus. Initialisiert die Laufzeit und erstellt die Standardeinstellung <xref:System.AppDomain>.|  
|`COINITEE_DLL`|Führen Sie eine verwaltete DLL initialisiert.|  
|`COINITEE_MAIN`|Führen Sie eine verwaltete EXE-Datei initialisiert. Dies initialisiert die Laufzeit, jedoch nicht die Standardeinstellung erstellt <xref:System.AppDomain>, die nach der Eingabe der Hauptroutine der EXE-Datei erstellt wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
