---
title: CorRefToDefCheck-Enumeration
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e7ce604acddb88d5a15844cbce2622b21e364cc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706111"
---
# <a name="correftodefcheck-enumeration"></a>CorRefToDefCheck-Enumeration

Gibt Flags an, mit denen gesteuert wird, welche Elemente, auf die verwiesen wird, zur Optimierung des Codes in ihre Definitionen konvertiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`MDRefToDefDefault`|Gibt an, dass Typverweise und Element Verweise in Definitionen konvertiert werden sollen. Dies ist der Standardwert ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).|  
|`MDRefToDefAll`|Gibt an, dass alle referenzierten Elemente in Definitionen konvertiert werden sollen.|  
|`MDRefToDefNone`|Gibt an, dass keine referenzierten Elemente in Definitionen konvertiert werden sollen.|  
|`MDTypeRefToDef`|Gibt an, dass nur Typverweise in Typdefinitionen konvertiert werden sollen.|  
|`MDMemberRefToDef`|Gibt an, dass nur Member-Verweise in Definitionen konvertiert werden sollen. Das heißt, dass Element Verweise entweder in Methoden Definitionen oder Feld Definitionen konvertiert werden sollen.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
