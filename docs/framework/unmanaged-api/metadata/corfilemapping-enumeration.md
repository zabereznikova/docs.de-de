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
ms.openlocfilehash: f85a36c810df52f871ecc75b92a3b4440455c66b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450298"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping-Enumeration
Enthält Werte, die den Typ der Datei Zuordnung beschreiben, der von einem Aufrufen der [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) -Methode zurückgegeben wird.  
  
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
|`fmFlat`|Die Datei wird als Datendatei zugeordnet. Das heißt, das `SEC_IMAGE`-Flag wurde nicht an die Microsoft Win32 `CreateFileMapping`-Funktion übermittelt.|  
|`fmExecutableImage`|Die Datei wird für die Ausführung zugeordnet, entweder mithilfe der `LoadLibrary`-Funktion oder der `CreateFileMapping`-Funktion mit dem `SEC_IMAGE`-Flag.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [GetFileMapping-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
