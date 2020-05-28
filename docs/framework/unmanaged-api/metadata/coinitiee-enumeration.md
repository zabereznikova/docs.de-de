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
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005907"
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Standard Initialisierungs Modus. Dadurch wird die Laufzeit initialisiert und der Standardwert erstellt <xref:System.AppDomain> .|  
|`COINITEE_DLL`|Initialisiert, um eine verwaltete DLL auszuführen.|  
|`COINITEE_MAIN`|Initialisiert, um eine verwaltete exe auszuführen. Dies initialisiert die Laufzeit, erstellt jedoch nicht den Standardwert <xref:System.AppDomain> , der nach der Eingabe der Haupt Routine der exe-Datei erstellt wird.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
