---
title: AssemblyRefFlags-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 0a99d2f79645bdc46ff4db86d7280614eeb1faf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732761"
---
# <a name="assemblyrefflags-enumeration"></a>AssemblyRefFlags-Enumeration

Enthält Werte, die Funktionen eines Assemblyverweises beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`arfFullOriginator`|Gibt an, dass der Assemblyverweis vollständige, unverschlüsselte Informationen zum Verleger der Assembly enthält.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
- [DefineAssemblyRef-Methode](imetadataassemblyemit-defineassemblyref-method.md)
