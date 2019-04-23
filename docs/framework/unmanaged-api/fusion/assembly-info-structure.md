---
title: ASSEMBLY_INFO-Struktur
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bae19ec18c54eccc7aa54d2d3a006f36ba8ab762
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110876"
---
# <a name="assemblyinfo-structure"></a>ASSEMBLY_INFO-Struktur
Enthält Informationen zu einer Assembly, die im globalen Assemblycache registriert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`cbAssemblyInfo`|Die Größe der Struktur in Bytes. Dieses Feld ist für zukünftige Erweiterungen reserviert.|  
|`dwAssemblyFlags`|Flags, die Details zur Installation über die Assembly anzugeben. Die folgenden Werte werden unterstützt:<br /><br /> – Die ASSEMBLYINFO_FLAG_INSTALLED-Wert, der angibt, dass die Assembly installiert ist. Legt die aktuelle Version von .NET Framework `dwAssemblyFlags` auf diesen Wert.<br />– Die ASSEMBLYINFO_FLAG_PAYLOADRESIDENT-Wert, der angibt, dass die Assembly eine Nutzlast erhält vom residenten ist. Die aktuelle Version von .NET Framework nie legt `dwAssemblyFlags` auf diesen Wert.|  
|`uliAssemblySizeInKB`|Die Gesamtgröße in KB, Dateien, die die Assembly enthält.|  
|`pszCurrentAssemblyPathBuf`|Ein Zeiger auf einen Zeichenfolgenpuffer, der den aktuellen Pfad in die Manifestdatei enthält. Der Pfad muss mit einem Null-Zeichen enden.|  
|`cchBuf`|Die Anzahl der Breitzeichen, einschließlich des null-Abschlusszeichens, `pszCurrentAssemblyPathBuf` enthält.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Strukturen](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [Globaler Assemblycache](../../../../docs/framework/app-domains/gac.md)
