---
title: CorPEKind-Enumeration
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045538"
---
# <a name="corpekind-enumeration"></a>CorPEKind-Enumeration
Enthält Werte, die beschreiben, eine Datei (portable Executable)-Datei von einem Aufruf zurückgegeben [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`peNot`|Gibt an, dass es sich nicht um eine PE-Datei handelt.|  
|`peILOnly`|Gibt an, dass diese PE-Datei enthält nur verwalteten Code.|  
|`pe32BitRequired`|Gibt an, dass diese PE-Datei mit Win32-Aufrufe ausführt.|  
|`pe32Plus`|Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.|  
|`pe32Unmanaged`|Gibt an, dass diese PE-Datei mit systemeigenem Code ist.|  
|pe32BitPreferred|Gibt an, dass diese PE-Datei plattformunabhängig ist und zieht es vor, die in einer 32-Bit-Umgebung geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte können in bitweise Kombinationen verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
