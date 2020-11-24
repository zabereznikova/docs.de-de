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
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690940"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA-Struktur

Stellt Informationen für den Symbol Handler über Methoden bereit, die aufgrund von Änderungen verschoben wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`mdMethod`|Das Metadatentoken der Methode.|  
|`delta`|Die Anzahl der Zeilen, die die Methode verschoben wurde.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Strukturen](diagnostics-symbol-store-structures.md)
