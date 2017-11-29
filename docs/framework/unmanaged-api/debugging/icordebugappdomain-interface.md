---
title: ICorDebugAppDomain Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain
helpviewer_keywords: ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19cf38920ed818dfbba9cd83bd64fdc408281e0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain-interface1"></a>ICorDebugAppDomain Schnittstelle1
Stellt Methoden zum Debuggen von Anwendungsdomänen bereit. Diese Schnittstelle ist eine Unterklasse von ICorDebugController.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Attach-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Fügt der Debugger an die Anwendungsdomäne.|  
|[EnumerateAssemblies-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.|  
|[EnumerateBreakpoints-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Ruft einen Enumerator für alle aktiven Haltepunkte in der Anwendungsdomäne ab.|  
|[EnumerateSteppers-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Ruft einen Enumerator für alle aktiven Stepper in der Anwendungsdomäne ab.|  
|[GetId-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Ruft die eindeutige ID der Anwendungsdomäne ab.|  
|[GetModuleFromMetaDataInterface-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Ruft die ICorDebugModule-Objekt mit der angegebenen Metadaten-Schnittstelle ab.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Ruft den Namen der Anwendungsdomäne ab.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR) Anwendungsdomäne ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Ruft den Prozess ab, die die Anwendungsdomäne enthält.|  
|[IsAttached-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Bestimmt, ob der Debugger an die Anwendungsdomäne angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
