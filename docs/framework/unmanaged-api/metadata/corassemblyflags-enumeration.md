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
ms.openlocfilehash: eca4b66a3f7c1a96bb06827dde477f34cb904ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906242"
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
|`afPublicKey`|Gibt an, dass der Assemblyverweis auf den öffentlichen Schlüssel für vollständigen, nicht gehashte enthält.|  
|`afPA_None`|Gibt an, dass die Prozessorarchitektur nicht angegeben wird.|  
|`afPA_MSIL`|Gibt an, dass die Prozessorarchitektur neutral ist (PE32).|  
|`afPA_x86`|Gibt an, dass die Prozessorarchitektur X86 (PE32) ist.|  
|`afPA_IA64`|Gibt an, dass die Prozessorarchitektur Itanium (PE32 +) ist.|  
|`afPA_AMD64`|Gibt an, dass die Prozessorarchitektur AMD X64 (PE32 +) ist.|  
|`afPA_ARM`|Gibt an, dass die Prozessorarchitektur ARM (PE32) ist.|  
|`afPA_NoPlatform`|Gibt an, dass die Assembly eine Verweisassembly; Das heißt, es gilt für jede Architektur, jedoch kann nicht auf jeder Architektur ausgeführt werden. Daher das Flag ist identisch mit `afPA_Mask`.|  
|`afPA_Specified`|Gibt an, dass die Flags der Prozessorarchitektur soll, um weitergegeben werden die `AssemblyRef` Datensatz.|  
|`afPA_Mask`|Eine Maske, die die Prozessorarchitektur beschreibt.|  
|`afPA_FullMask`|Gibt an, dass die Beschreibung der Prozessorarchitektur enthalten ist.|  
|`afPA_Shift`|Gibt ein Verschiebungswert in die Flags der Prozessorarchitektur in und aus dem Index an.|  
|`afEnableJITcompileTracking`|Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von der <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von der <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Gibt an, dass die Assembly zur Laufzeit auf eine Assembly von einem anderen Verleger umgeleitet werden kann.|  
|`afContentType_Mask`|Eine Maske, die den Inhaltstyp beschreibt.|  
|`afContentType_Default`|Gibt den Standardinhaltstyp an.|  
|`afContentType_WindowsRuntime`|Gibt an, die [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Inhaltstyp.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
