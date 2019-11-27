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
ms.openlocfilehash: 2d49a146a465210cea8466a75666ca3f800b090b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450144"
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`prSpecialName`|Gibt an, dass die Eigenschaft speziell ist, und dass Ihr Name beschreibt, wie.|  
|`prReservedMask`|Reserviert für die interne Verwendung durch den Common Language Runtime.|  
|`prRTSpecialName`|Gibt an, dass die Common Language Runtime Metadaten-internen APIs die Codierung des Eigenschafts namens überprüfen sollen.|  
|`prHasDefault`|Gibt an, dass die Eigenschaft über einen Standardwert verfügt.|  
|`prUnused`|Nicht verwendet.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
