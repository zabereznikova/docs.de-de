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
ms.openlocfilehash: 673450bb8209abede15e3cb65dd764b418073bc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724194"
---
# <a name="coinitiee-enumeration"></a>COINITIEE-Enumeration

Gibt Konstanten an, die von [CoInitializeEE](../hosting/coinitializeee-function.md) beim Initialisieren der Common Language Runtime verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Standard Initialisierungs Modus. Dadurch wird die Laufzeit initialisiert und der Standardwert erstellt <xref:System.AppDomain> .|  
|`COINITEE_DLL`|Initialisiert, um eine verwaltete DLL auszuführen.|  
|`COINITEE_MAIN`|Initialisiert, um eine verwaltete exe auszuführen. Dies initialisiert die Laufzeit, erstellt jedoch nicht den Standardwert <xref:System.AppDomain> , der nach der Eingabe der Haupt Routine der exe-Datei erstellt wird.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
