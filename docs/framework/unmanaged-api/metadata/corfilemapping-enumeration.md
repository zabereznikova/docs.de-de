---
title: CorFileMapping-Enumeration
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726115"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping-Enumeration

Enthält Werte, die den Typ der Datei Zuordnung beschreiben, der von einem Aufrufen der [IMetaDataInfo:: GetFileMapping](imetadatainfo-getfilemapping-method.md) -Methode zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`fmFlat`|Die Datei wird als Datendatei zugeordnet. Das heißt, dass das `SEC_IMAGE` Flag nicht an die Microsoft Win32-Funktion übermittelt wurde `CreateFileMapping` .|  
|`fmExecutableImage`|Die Datei wird für die Ausführung zugeordnet, entweder mithilfe der- `LoadLibrary` Funktion oder der- `CreateFileMapping` Funktion mit dem- `SEC_IMAGE` Flag.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
- [GetFileMapping-Methode](imetadatainfo-getfilemapping-method.md)
