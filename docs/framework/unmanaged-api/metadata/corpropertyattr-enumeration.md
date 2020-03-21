---
title: CorPropertyAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: 95a798d662b44cf2e088af84d3b1eec97da8e7fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177944"
---
# <a name="corpropertyattr-enumeration"></a>CorPropertyAttr-Enumeration
Enthält Werte, in denen die Metadaten einer Eigenschaft beschrieben werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`prSpecialName`|Gibt an, dass die Eigenschaft speziell ist und dass ihr Name beschreibt, wie.|  
|`prReservedMask`|Reserviert für die interne Verwendung durch die Common Language Runtime.|  
|`prRTSpecialName`|Gibt an, dass die internen APIs für Common Language-Laufzeitmetadaten die Codierung des Eigenschaftennamens überprüfen sollen.|  
|`prHasDefault`|Gibt an, dass die Eigenschaft einen Standardwert besitzt.|  
|`prUnused`|Nicht verwendet.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
