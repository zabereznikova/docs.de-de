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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a54b20ecf34ecf1824420fcbb3d45fba64017b76
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657193"
---
# <a name="correftodefcheck-enumeration"></a>CorRefToDefCheck-Enumeration
Gibt Flags an, mit denen gesteuert wird, welche Elemente, auf die verwiesen wird, zur Optimierung des Codes in ihre Definitionen konvertiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDRefToDefDefault`|Gibt an, dass Verweise auf Typen und memberverweisen auf Definitionen konvertiert werden sollen. Dies ist der Standardwert (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).|  
|`MDRefToDefAll`|Gibt an, dass alle referenzierten Elemente in Definitionen konvertiert werden soll.|  
|`MDRefToDefNone`|Gibt an, dass keine Elemente auf die verwiesen wird, die in Definitionen konvertiert werden soll.|  
|`MDTypeRefToDef`|Gibt an, dass nur Verweise auf Typen um zu Typdefinitionen konvertiert werden sollen.|  
|`MDMemberRefToDef`|Gibt an, dass nur memberverweisen auf Definitionen konvertiert werden sollen. D. h. sollen Elementverweise Methodendefinitionen oder Felddefinitionen konvertiert werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
