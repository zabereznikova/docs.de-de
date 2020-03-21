---
title: CorSymVarFlag-Enumeration
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: 21e92d8f2fb80c4c41d516ef281bf4fc8a75f4e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176642"
---
# <a name="corsymvarflag-enumeration"></a>CorSymVarFlag-Enumeration
Gibt an, ob eine Variable vom Compiler generiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|Gibt an, dass die angegebene Variable vom Compiler generiert wird.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Kopfzeile:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
