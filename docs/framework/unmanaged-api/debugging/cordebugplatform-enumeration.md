---
title: CorDebugPlatform-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
ms.openlocfilehash: 2ed32449c4a133e6e72ec44f9cb57f49de22164a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778233"
---
# <a name="cordebugplatform-enumeration"></a>CorDebugPlatform-Enumeration
Stellt Ziel Platt Form Werte bereit, die von der [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|Die Zielplattform ist Windows auf Intel-x86-Hardware.|  
|CORDB_PLATFORM_WINDOWS_AMD64|Die Zielplattform ist 64-Bit-Windows auf AMD64-Hardware oder Intel EM64T-Hardware.|  
|CORDB_PLATFORM_WINDOWS_IA64|Die Zielplattform ist 32-Bit-Windows auf Intel IA-64-Hardware.|  
|CORDB_PLATFORM_MAC_PPC|Die Zielplattform ist das Macintosh-Betriebssystem, das auf PowerPC-Hardware ausgeführt wird.|  
|CORDB_PLATFORM_MAC_X86|Die Zielplattform ist das Macintosh-Betriebssystem, das auf Intel x86-Hardware ausgeführt wird.|  
|CORDB_PLATFORM_WINDOWS_ARM|Die Zielplattform ist das Macintosh-Betriebssystem, das auf Windows-Arm-Hardware ausgeführt wird.|  
|CORDB_PLATFORM_MAC_AMD64|Die Zielplattform ist das Macintosh-Betriebssystem, das auf AMD64-Hardware ausgeführt wird.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 Die `CORDB_PLATFORM_WINDOWS_ARM`- und `CORDB_PLATFORM_MAC_AMD64`-Member sind in .NET Framework 4.5.2 und höheren Versionen verfügbar.  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](debugging-enumerations.md)
