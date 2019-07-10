---
title: CorOpenFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 831f4665967f2cd07a7ebb4de750fbe456a82261
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781686"
---
# <a name="coropenflags-enumeration"></a>CorOpenFlags-Enumeration
Enthält Flagwerte, die das Verhalten von Metadaten beim Öffnen von Manifestdateien steuern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`ofRead`|Gibt an, dass die Datei nur zum Lesen geöffnet werden darf.|  
|`ofWrite`|Gibt an, dass die Datei nur zum Schreiben geöffnet werden darf.<br /><br /> Wenn Sie beim Öffnen einer .winmd-Datei das `ofWrite`-Flag verwenden, sollten Sie auch das `ofNoTransform`-Flag übergeben.|  
|`ofReadWriteMask`|Eine Maske zum Lesen und Schreiben.|  
|`ofCopyMemory`|Gibt an, dass die Datei in den Arbeitsspeicher gelesen werden muss. Metadaten müssen eine eigene Kopie verwalten.|  
|`ofCacheImage`|Veraltet. Dieses Flag wird ignoriert.|  
|`ofManifestMetadata`|Veraltet. Dieses Flag wird ignoriert.|  
|`ofReadOnly`|Gibt an, dass die Datei zum Lesen und, die geöffnet werden darf einen Aufruf von `QueryInterface` für eine [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) kann nicht hergestellt werden.|  
|`ofTakeOwnership`|Gibt an, dass der Speicher belegt wurde über einen Aufruf an [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) und von den Metadaten freigegeben wird.|  
|`ofNoTypeLib`|Veraltet. Dieses Flag wird ignoriert.|  
|`ofNoTransform`|Gibt an, dass automatische Transformationen von .winmd-Dateien deaktiviert sein sollten. Anders ausgedrückt: Die Projektion eines Windows Runtime-Typs auf einen .NET Framework-Typ sollte deaktiviert sein. Weitere Informationen finden Sie unter [Windows-Runtime und CLR - darunter das System mit .NET und die Windows-Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).|  
|`ofReserved1`|Für die interne Verwendung vorgesehen.|  
|`ofReserved2`|Für die interne Verwendung vorgesehen.|  
|`ofReserved`|Für die interne Verwendung vorgesehen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
