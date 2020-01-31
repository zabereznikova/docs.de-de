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
ms.openlocfilehash: 3654c94975d16e35d5c3d8e762730d17509a2c6d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788880"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform-Methode
Bietet Informationen zur-Plattform, einschließlich Prozessorarchitektur und Betriebssystem, auf denen der Ziel Prozess ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parameters  
 `pTargetPlatform`  
 vorgenommen Ein Zeiger auf eine [cordebugplatformenum](cordebugplatform-enumeration.md) -Enumeration, die die Zielplattform beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Der `CorDebugPlatformEnum` enumerationsrückgabetyp wird von der [ICorDebug](icordebug-interface.md) -Schnittstelle verwendet, um Details des Ziel Prozesses zu bestimmen, z. b. Zeiger Größe, Adressraum Layout, Register Satz, Anweisungs Format, Kontext Layout und Aufruf Konventionen.  
  
 Der `pTargetPlatform` Wert bezieht sich möglicherweise auf eine Plattform, die für das Ziel emuliert wird, anstatt die tatsächlich verwendete Hardware anzugeben. Beispielsweise sollte ein Prozess, der in der WOW-Umgebung (Windows on Windows) auf einer 64-Bit-Edition des Windows-Betriebssystems ausgeführt wird, den `CORDB_PLATFORM_WINDOWS_X86` Wert der [cordebugplatformenum](cordebugplatform-enumeration.md) -Enumeration verwenden.  
  
 Diese Methode muss erfolgreich sein. Wenn dies nicht möglich ist, ist die Zielplattform unbrauchbar. Die-Methode kann aus den folgenden Gründen fehlschlagen:  
  
- Die Plattform, die für das Ziel emuliert wird, ist unbrauchbar.  
  
- Die tatsächliche Hardware auf der Zielplattform ist unbrauchbar.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
