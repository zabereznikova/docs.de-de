---
title: COR_PRF_STATIC_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 880c9bd186d6cb2acb277e9cc55d3063fb8d51d8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867034"
---
# <a name="cor_prf_static_type-enumeration"></a>COR_PRF_STATIC_TYPE-Enumeration
Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt. Diese Werte können mithilfe der bitweisen OR-Operation kombiniert werden, um anzugeben, dass das Feld über mehrere unterschiedliche statische Qualitäten verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|Das Feld ist nicht statisch.|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|Das Feld ist Anwendungsdomäne (statisch).|  
|`COR_PRF_FIELD_THREAD_STATIC`|Das Feld ist Thread statisch.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|Das Feld ist Kontext statisch.|  
|`COR_PRF_FIELD_RVA_STATIC`|Das Feld ist eine relative virtuelle Adresse (RVA)-static.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](profiling-enumerations.md)
