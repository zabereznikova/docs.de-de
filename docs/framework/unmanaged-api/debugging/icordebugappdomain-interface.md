---
title: ICorDebugAppDomain-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: 140e67417f4fad552f972a93bc8c620b440b2370
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895175"
---
# <a name="icordebugappdomain-interface"></a>ICorDebugAppDomain-Schnittstelle

Stellt Methoden zum Debuggen von Anwendungsdomänen bereit. Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Attach-Methode](icordebugappdomain-attach-method.md)|Fügt den Debugger an die Anwendungsdomäne an.|  
|[EnumerateAssemblies-Methode](icordebugappdomain-enumerateassemblies-method.md)|Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.|  
|[EnumerateBreakpoints-Methode](icordebugappdomain-enumeratebreakpoints-method.md)|Ruft einen Enumerator für alle aktiven Breakpoints in der Anwendungsdomäne ab.|  
|[EnumerateSteppers-Methode](icordebugappdomain-enumeratesteppers-method.md)|Ruft einen Enumerator für alle aktiven Steppers in der Anwendungsdomäne ab.|  
|[GetId-Methode](icordebugappdomain-getid-method.md)|Ruft die eindeutige ID der Anwendungsdomäne ab.|  
|[GetModuleFromMetaDataInterface-Methode](icordebugappdomain-getmodulefrommetadatainterface-method.md)|Ruft das ICorDebug Module-Objekt mit der angegebenen Metadatenschnittstelle ab.|  
|[GetName-Methode](icordebugappdomain-getname-method.md)|Ruft den Namen der Anwendungsdomäne ab.|  
|[GetObject-Methode](icordebugappdomain-getobject-method.md)|Ruft einen Schnittstellen Zeiger auf die Common Language Runtime (CLR)-Anwendungsdomäne ab.|  
|[GetProcess-Methode](icordebugappdomain-getprocess-method.md)|Ruft den Prozess ab, der die Anwendungsdomäne enthält.|  
|[IsAttached-Methode](icordebugappdomain-isattached-method.md)|Bestimmt, ob der Debugger an die Anwendungsdomäne angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
