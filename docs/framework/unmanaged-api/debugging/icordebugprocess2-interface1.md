---
title: ICorDebugProcess2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2
helpviewer_keywords: ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1a73874f6ca2f839639cbaf731a59721b2aede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2-interface1"></a>ICorDebugProcess2 Schnittstelle1
Eine logische Erweiterung der ICorDebugProcess-Schnittstelle, die eine Prozess Ausführung von verwaltetem Code darstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|Entfernt einen Haltepunkt am angegebenen Offset begonnen, die durch einen früheren Aufruf festgelegter `ICorDebugProcess2::SetUnmanagedBreakpoint`.|  
|[GetDesiredNGENCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|Ruft die Flags ab, die für die common Language Runtime (CLR) müssen, beim Laden des Bilds in den Prozess festgelegt werden, auf die verwiesen wird von diesem `ICorDebugProcess2`.|  
|[GetReferenceValueFromGCHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|Ruft einen Verweiszeiger auf dem angegebenen verwalteten Objekt, das eine Garbagecollection-handle verfügt.|  
|[GetThreadForTaskID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|Ruft den Thread, auf dem die Aufgabe mit dem angegebenen Bezeichner ausgeführt wird.|  
|[GetVersion-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|Ruft die Version der CLR, auf denen der zu debuggende Prozess ausgeführt wird.|  
|[SetDesiredNGENCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|Legt die Flags, die für den Just-in-Time (JIT)-Compiler, ein Bild in den zu debuggenden Prozess zu laden erforderlich sind.|  
|[SetUnmanagedBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|Legt einen Haltepunkt auf nicht verwalteten Offset angegebene systemeigene Image fest.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
