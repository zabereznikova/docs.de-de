---
title: COR_VERSION-Struktur
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
ms.openlocfilehash: 874c0520482cc5a3bbfcdd17924edee84fe91ff5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675320"
---
# <a name="cor_version-structure"></a>COR_VERSION-Struktur

Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`dwMajor`|Die Hauptversionsnummer.|  
|`dwMinor`|Die Nebenversionsnummer.|  
|`dwBuild`|Die Buildnummer.|  
|`dwSubBuild`|Die teilbuildnummer.|  
  
## <a name="remarks"></a>Hinweise  

 Wenn die Versionsnummer 1.0.3705.288 ist, ist 1 die Hauptversionsnummer, 0 ist die neben Versionsnummer, 3705 ist die Buildnummer, und 288 ist die teilbuildnummer.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
