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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6ec37bbd8750c27a41b5f18180c7726cdcd483
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags-Enumeration
Enthält Werte, die die auf eine Assemblykompilierung angewendeten Metadaten beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`afPublicKey`|Gibt an, dass der Assemblyverweis die vollständigen, nicht gehashte öffentlichen Schlüssel enthält.|  
|`afPA_None`|Gibt an, dass die Prozessorarchitektur nicht angegeben wird.|  
|`afPA_MSIL`|Gibt an, dass die Prozessorarchitektur neutral ist (PE32).|  
|`afPA_x86`|Gibt an, dass die Prozessorarchitektur X86 (PE32) ist.|  
|`afPA_IA64`|Gibt an, dass die Prozessorarchitektur Itanium (PE32 +) ist.|  
|`afPA_AMD64`|Gibt an, dass die Prozessorarchitektur AMD X64 (PE32 +) ist.|  
|`afPA_ARM`|Gibt an, dass die Prozessorarchitektur ARM (PE32) ist.|  
|`afPA_NoPlatform`|Gibt an, dass die Assembly eine Verweisassembly ist; d. h. gilt für jede Architektur, aber nicht auf jeder Architektur ausgeführt wird. Daher das Flag ist identisch mit `afPA_Mask`.|  
|`afPA_Specified`|Gibt an, dass die Flags der Prozessorarchitektur an weitergegeben werden soll die `AssemblyRef` Datensatz.|  
|`afPA_Mask`|Eine Maske, die die Prozessorarchitektur beschreibt.|  
|`afPA_FullMask`|Gibt an, dass die Beschreibung der Prozessorarchitektur enthalten ist.|  
|`afPA_Shift`|Gibt eine Anzahl UMSCHALT in Flags der Prozessorarchitektur verschiedene andere und aus dem Index.|  
|`afEnableJITcompileTracking`|Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von der <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von der <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Gibt an, dass die Assembly zur Laufzeit auf eine Assembly von einem anderen Herausgeber umgeleitet werden kann.|  
|`afContentType_Mask`|Eine Maske, die den Inhaltstyp beschreibt.|  
|`afContentType_Default`|Gibt den Standardinhaltstyp an.|  
|`afContentType_WindowsRuntime`|Gibt an, die [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Inhaltstyp.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
