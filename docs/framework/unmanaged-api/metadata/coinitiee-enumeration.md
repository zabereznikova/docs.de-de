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
ms.openlocfilehash: 2ccc038b4420040779dae70f15e3a8827ba94180
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444105"
---
# <a name="coinitiee-enumeration"></a>COINITIEE-Enumeration
Gibt Konstanten an, die von [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) beim Initialisieren der Common Language Runtime verwendet werden.  
  
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
|`COINITEE_DEFAULT`|Standard Initialisierungs Modus. Dadurch wird die Laufzeit initialisiert und die Standard <xref:System.AppDomain>erstellt.|  
|`COINITEE_DLL`|Initialisiert, um eine verwaltete DLL auszuführen.|  
|`COINITEE_MAIN`|Initialisiert, um eine verwaltete exe auszuführen. Dadurch wird die Common Language Runtime initialisiert, aber nicht die Standard <xref:System.AppDomain>erstellt, die nach der Eingabe der Haupt Routine der exe-Datei erstellt wird.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
