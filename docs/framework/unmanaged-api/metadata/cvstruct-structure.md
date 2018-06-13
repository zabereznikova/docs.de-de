---
title: CVStruct-Struktur
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 195f311d58f2169d715bb33986ee6e591622f377
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445042"
---
# <a name="cvstruct-structure"></a>CVStruct-Struktur
Enthält Informationen, die bei der Installation eines Moduls oder eines zusammengesetzten Abbilds verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|Hauptversion|Nummer der Hauptversion-Builds.|  
|Gering|Nummer der Nebenversion Build.|  
|Sub|Sub-Buildnummer.|  
|Build|Buildnummer.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
