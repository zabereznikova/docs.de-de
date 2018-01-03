---
title: ICorDebugDataTarget::GetPlatform-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetPlatform Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c19e472ef571def1011d2a00701fea3a6fadfea8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform-Methode
Enthält Informationen über die Plattform, einschließlich der Prozessorarchitektur und Betriebssystem, auf denen der Zielprozess ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pTargetPlatform`  
 [out] Ein Zeiger auf eine [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) Enumeration, die die Zielplattform beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `CorDebugPlatformEnum` return Enumerationswert wird verwendet, durch die [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle, um die Details des Zielprozesses, z. B. die Zeigergröße, Adresse Speicherplatz Layout, Registersatz, Anweisungsformat, Kontextlayout zu bestimmen und Aufrufkonventionen.  
  
 Die `pTargetPlatform` Wert bezieht sich möglicherweise auf eine Plattform, die für das Ziel die tatsächliche Hardware verwendet angeben, statt emuliert wird. Beispielsweise ein Prozess, der in dem Windows on Windows (WOW)-Umgebung auf eine 64-Bit-Edition von Windows-Betriebssystem ausgeführt wird die zu verwendende der `CORDB_PLATFORM_WINDOWS_X86` Wert, der die [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) Enumeration.  
  
 Diese Methode muss erfolgreich sein. Falls dies fehlschlägt, ist die Zielplattform unbrauchbar. Die Methode kann den folgenden Gründen fehlschlagen:  
  
-   Die Plattform, die für das Ziel emulierte ist unbrauchbar.  
  
-   Die tatsächliche Hardware für die Zielplattform ist unbrauchbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
