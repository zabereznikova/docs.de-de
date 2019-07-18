---
title: SYMLINEDELTA-Struktur
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d98ebed2eb853d5dc8177b0b044bf654c3978494
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744351"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA-Struktur
Enthält Informationen, die an den Symbol-Handler zu Methoden, die Bearbeitungsvorgängen verschoben wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`mdMethod`|Die Methode die Metadaten-Token.|  
|`delta`|Die Anzahl der Zeilen, die die Methode verschoben wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Strukturen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
