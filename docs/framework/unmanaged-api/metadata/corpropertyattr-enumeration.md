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
ms.openlocfilehash: d76de80f87a8e5a63eac9f6a413f2efb0e394b0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706124"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`prSpecialName`|Gibt an, dass die Eigenschaft speziell ist, und dass Ihr Name beschreibt, wie.|  
|`prReservedMask`|Reserviert für die interne Verwendung durch den Common Language Runtime.|  
|`prRTSpecialName`|Gibt an, dass die Common Language Runtime Metadaten-internen APIs die Codierung des Eigenschafts namens überprüfen sollen.|  
|`prHasDefault`|Gibt an, dass die Eigenschaft einen Standardwert besitzt.|  
|`prUnused`|Nicht verwendet.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
