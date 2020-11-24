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
ms.openlocfilehash: e8612b23cbfa506fddb2fad712848b285b9ac28e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679792"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform-Methode

Bietet Informationen zur-Plattform, einschließlich Prozessorarchitektur und Betriebssystem, auf denen der Ziel Prozess ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parameter  

 `pTargetPlatform`  
 vorgenommen Ein Zeiger auf eine [cordebugplatformenum](cordebugplatform-enumeration.md) -Enumeration, die die Zielplattform beschreibt.  
  
## <a name="remarks"></a>Hinweise  

 Der `CorDebugPlatformEnum` Rückgabewert der-Enumeration wird von der [ICorDebug](icordebug-interface.md) -Schnittstelle verwendet, um Details des Ziel Prozesses zu bestimmen, z. b. die Zeiger Größe, das Adressraum Layout, den Register Satz, das Anweisungs Format, das Kontext Layout und die Aufruf Konventionen.  
  
 Der `pTargetPlatform` Wert verweist möglicherweise auf eine Plattform, die für das Ziel emuliert wird, anstatt die tatsächlich verwendete Hardware anzugeben. Beispielsweise sollte ein Prozess, der in der WOW-Umgebung (Windows on Windows) auf einer 64-Bit-Edition des Windows-Betriebssystems ausgeführt wird, den `CORDB_PLATFORM_WINDOWS_X86` Wert der [cordebugplatformenum](cordebugplatform-enumeration.md) -Enumeration verwenden.  
  
 Diese Methode muss erfolgreich sein. Wenn dies nicht möglich ist, ist die Zielplattform unbrauchbar. Die-Methode kann aus den folgenden Gründen fehlschlagen:  
  
- Die Plattform, die für das Ziel emuliert wird, ist unbrauchbar.  
  
- Die tatsächliche Hardware auf der Zielplattform ist unbrauchbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
