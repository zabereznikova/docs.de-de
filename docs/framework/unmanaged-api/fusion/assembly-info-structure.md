---
title: ASSEMBLY_INFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`cbAssemblyInfo`|Die Größe in Bytes, der Struktur. Dieses Feld ist für zukünftige Erweiterungen reserviert.|  
|`dwAssemblyFlags`|Flags, die Details zur Installation über die Assembly angeben. Die folgenden Werte werden unterstützt:<br /><br /> – Der ASSEMBLYINFO_FLAG_INSTALLED-Wert, der angibt, dass die Assembly installiert ist. Legt die aktuelle Version von .NET Framework `dwAssemblyFlags` mit diesem Wert.<br />– Der ASSEMBLYINFO_FLAG_PAYLOADRESIDENT-Wert, der gibt an, dass die Assembly eine residenten Nutzlast ist. Die aktuelle Version von .NET Framework nie legt `dwAssemblyFlags` mit diesem Wert.|  
|`uliAssemblySizeInKB`|Die Gesamtgröße der Dateien, die die Assembly enthält in Kilobytes.|  
|`pszCurrentAssemblyPathBuf`|Ein Zeiger auf einen Zeichenfolgenpuffer, der den aktuellen Pfad der Manifestdatei enthält. Der Pfad muss mit einem Null-Zeichen enden.|  
|`cchBuf`|Die Anzahl der Breitzeichen, einschließlich der null-Abschlusszeichen, `pszCurrentAssemblyPathBuf` enthält.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Strukturen](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Globaler Assemblycache](../../../../docs/framework/app-domains/gac.md)
