---
title: StackOverflowType-Enumeration
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: bbdc68721378e6bbb09f5e4eade08e2e6e03b097
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729910"
---
# <a name="stackoverflowtype-enumeration"></a>StackOverflowType-Enumeration

Enthält Werte, die die zugrunde liegende Ursache eines Stapelüberlauf Ereignisses angeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`SO_ClrEngine`|Der Stapelüberlauf wurde von der Ausführungs-Engine verursacht.|  
|`SO_Managed`|Der Stapelüberlauf wurde durch verwalteten Code verursacht.|  
|`SO_Other`|Der Stapelüberlauf wurde durch nicht verwalteten Code verursacht.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Informationen werden an den Host über einen aufzurufenden Befehl der [iaktiononclrevent:: OnEvent](iactiononclrevent-onevent-method.md) -Methode übermittelt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Enumerationen](hosting-enumerations.md)
