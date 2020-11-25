---
title: CorAssemblyFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
ms.openlocfilehash: 615c4ac95ab777e8081e630cafb6671e64dea78a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718994"
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags-Enumeration

Enthält Werte, die die auf eine Assemblykompilierung angewendeten Metadaten beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`afPublicKey`|Gibt an, dass der Assemblyverweis den vollständigen, unverschlüsselten öffentlichen Schlüssel enthält.|  
|`afPA_None`|Gibt an, dass die Prozessorarchitektur nicht angegeben ist.|  
|`afPA_MSIL`|Gibt an, dass die Prozessorarchitektur neutral ist (das Format PE32).|  
|`afPA_x86`|Gibt an, dass die Prozessorarchitektur x86 (das Format PE32) ist.|  
|`afPA_IA64`|Gibt an, dass die Prozessorarchitektur Itanium (das Format PE32 +) ist.|  
|`afPA_AMD64`|Gibt an, dass die Prozessorarchitektur AMD x64 (das Format PE32 +) ist.|  
|`afPA_ARM`|Gibt an, dass die Prozessorarchitektur Arm (das Format PE32) ist.|  
|`afPA_NoPlatform`|Gibt an, dass die Assembly eine Verweisassembly ist. Das heißt, es gilt für jede Architektur, kann aber nicht in einer Architektur ausgeführt werden. Folglich ist das-Flag identisch mit `afPA_Mask` .|  
|`afPA_Specified`|Gibt an, dass die Flags der Prozessorarchitektur an den Datensatz weitergegeben werden sollen `AssemblyRef` .|  
|`afPA_Mask`|Eine Maske, die die Prozessorarchitektur beschreibt.|  
|`afPA_FullMask`|Gibt an, dass die Beschreibung der Prozessorarchitektur enthalten ist.|  
|`afPA_Shift`|Gibt eine Verschiebungs Anzahl in der Prozessorarchitektur-Flags zum und aus dem Index an.|  
|`afEnableJITcompileTracking`|Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von an <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afDisableJITcompileOptimizer`|Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von an <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afRetargetable`|Gibt an, dass die Assembly zur Laufzeit auf eine Assembly von einem anderen Verleger neu zugewiesen werden kann.|  
|`afContentType_Mask`|Eine Maske, die den Inhaltstyp beschreibt.|  
|`afContentType_Default`|Gibt den Standard Inhaltstyp an.|  
|`afContentType_WindowsRuntime`|Gibt den Windows-Runtime Inhaltstyp an.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
