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
ms.openlocfilehash: ad582fc2fd1bd1d2fc9d5a0d483fdb3a51309a10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436508"
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
|`ofReadOnly`|Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.|  
|`ofTakeOwnership`|Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.|  
|`ofNoTypeLib`|Veraltet. Dieses Flag wird ignoriert.|  
|`ofNoTransform`|Gibt an, dass automatische Transformationen von .winmd-Dateien deaktiviert sein sollten. Anders ausgedrückt: Die Projektion eines Windows Runtime-Typs auf einen .NET Framework-Typ sollte deaktiviert sein. For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).|  
|`ofReserved1`|Für die interne Verwendung vorgesehen.|  
|`ofReserved2`|Für die interne Verwendung vorgesehen.|  
|`ofReserved`|Für die interne Verwendung vorgesehen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
