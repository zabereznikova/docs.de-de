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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 719f0522cc43625a4d6cc8afa838d869e47b40d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781834"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping-Enumeration
Enthält Werte, die den Typ der dateizuordnung zu beschreiben, die von einem Aufruf zurückgegeben wird, die [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`fmFlat`|Die Datei wird als eine Datendatei zugeordnet. D. h. die `SEC_IMAGE` Flag wurde nicht übergeben, der Microsoft Win32 `CreateFileMapping` Funktion.|  
|`fmExecutableImage`|Die Datei wird für die Ausführung zugeordnet, indem Sie entweder die `LoadLibrary` Funktion oder die `CreateFileMapping` -Funktion mit den `SEC_IMAGE` Flag.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [GetFileMapping-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
