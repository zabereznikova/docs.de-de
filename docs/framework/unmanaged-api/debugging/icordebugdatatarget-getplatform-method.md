---
title: ICorDebugDataTarget::GetPlatform-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: 5715f0634346dd0c6591cfe5687690aa0fba95f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125318"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform-Methode
Bietet Informationen zur-Plattform, einschließlich Prozessorarchitektur und Betriebssystem, auf denen der Ziel Prozess ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parameter  
 `pTargetPlatform`  
 vorgenommen Ein Zeiger auf eine [cordebugplatformenum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) -Enumeration, die die Zielplattform beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Der `CorDebugPlatformEnum` enumerationsrückgabetyp wird von der [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Schnittstelle verwendet, um Details des Ziel Prozesses zu bestimmen, z. b. Zeiger Größe, Adressraum Layout, Register Satz, Anweisungs Format, Kontext Layout und Aufruf Konventionen.  
  
 Der `pTargetPlatform` Wert bezieht sich möglicherweise auf eine Plattform, die für das Ziel emuliert wird, anstatt die tatsächlich verwendete Hardware anzugeben. Beispielsweise sollte ein Prozess, der in der WOW-Umgebung (Windows on Windows) auf einer 64-Bit-Edition des Windows-Betriebssystems ausgeführt wird, den `CORDB_PLATFORM_WINDOWS_X86` Wert der [cordebugplatformenum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) -Enumeration verwenden.  
  
 Diese Methode muss erfolgreich sein. Wenn dies nicht möglich ist, ist die Zielplattform unbrauchbar. Die-Methode kann aus den folgenden Gründen fehlschlagen:  
  
- Die Plattform, die für das Ziel emuliert wird, ist unbrauchbar.  
  
- Die tatsächliche Hardware auf der Zielplattform ist unbrauchbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
