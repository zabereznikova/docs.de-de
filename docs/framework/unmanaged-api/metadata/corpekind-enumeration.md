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
ms.openlocfilehash: b5869eb16bd768d58a6f27a83f2d8d51914a8aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corpekind-enumeration"></a>CorPEKind-Enumeration
Enthält Werte, die eine PE (portable Executable)-Datei wird beschrieben, wie von einem Aufruf zurückgegebene [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).  
  
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
|`peNot`|Gibt an, dass dies keiner PE-Datei ist.|  
|`peILOnly`|Gibt an, dass diese PE-Datei nur verwalteten Code enthält.|  
|`pe32BitRequired`|Gibt an, dass diese PE-Datei Win32 aufgerufen wird.|  
|`pe32Plus`|Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.|  
|`pe32Unmanaged`|Gibt an, dass diese PE-Datei mit systemeigenem Code ist.|  
|pe32BitPreferred|Gibt an, dass diese PE-Datei plattformunabhängiges ist verwendet und ob in einer 32-Bit-Umgebung geladen werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte können in bitweisen Kombinationen verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
