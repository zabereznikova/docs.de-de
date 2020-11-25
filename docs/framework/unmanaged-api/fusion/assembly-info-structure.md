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
ms.openlocfilehash: 520a24ced6e897d926ce68ef5973ab7083731b9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717629"
---
# <a name="assembly_info-structure"></a>ASSEMBLY_INFO-Struktur

Enthält Informationen zu einer Assembly, die im globalen Assemblycache registriert ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`cbAssemblyInfo`|Die Größe der-Struktur in Bytes. Dieses Feld ist für die spätere Erweiterbarkeit reserviert.|  
|`dwAssemblyFlags`|Flags, die Installationsdetails über die Assembly angeben. Die folgenden Werte werden unterstützt:<br /><br /> : Der ASSEMBLYINFO_FLAG_INSTALLED Wert, der angibt, dass die Assembly installiert ist. Die aktuelle Version des-.NET Framework legt immer `dwAssemblyFlags` auf diesen Wert fest.<br />-Der ASSEMBLYINFO_FLAG_PAYLOADRESIDENT Wert, der angibt, dass die Assembly eine Nutzlast ist. Die aktuelle Version des .NET Framework nie `dwAssemblyFlags` auf diesen Wert festgelegt.|  
|`uliAssemblySizeInKB`|Die Gesamtgröße der Dateien in Kilobyte, die in der Assembly enthalten sind.|  
|`pszCurrentAssemblyPathBuf`|Ein Zeiger auf einen Zeichen folgen Puffer, der den aktuellen Pfad zur Manifest-Datei enthält. Der Pfad muss mit einem NULL-Zeichen enden.|  
|`cchBuf`|Die Anzahl der breit Zeichen, einschließlich des NULL-Abschluss Zeichens, das `pszCurrentAssemblyPathBuf` enthält.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusionsstrukturen](fusion-structures.md)
- [Globaler Assemblycache](../../app-domains/gac.md)
