---
title: ICorDebugEval2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: e69b32430651edd0222db874e2659bd959f89549
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788712"
---
# <a name="icordebugeval2-interface"></a>ICorDebugEval2-Schnittstelle

Erweitert "ICorDebugEval", um Unterstützung für generische Typen bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[CallParameterizedFunction-Methode](icordebugeval2-callparameterizedfunction-method.md)|Richtet einen aufzurufenden ' ICorDebugFunction ' ein, der in einem Typ geschachtelt werden kann, dessen Konstruktor Typparameter annimmt, oder selbst Typparameter annehmen kann.|  
|[CreateValueForType-Methode](icordebugeval2-createvaluefortype-method.md)|Ruft einen Zeiger auf einen neuen "ICorDebugValue" des angegebenen Typs mit einem Anfangswert von NULL oder 0 (null) ab.|  
|[NewParameterizedArray-Methode](icordebugeval2-newparameterizedarray-method.md)|Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu.|  
|[NewParameterizedObject-Methode](icordebugeval2-newparameterizedobject-method.md)|Instanziiert ein neues parametrisiertes Typobjekt und ruft die Konstruktormethode des Objekts auf.|  
|[NewParameterizedObjectNoConstructor-Methode](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Instanziiert ein neues parametrisiertes Typobjekt der angegebenen Klasse, ohne dass versucht wird, eine Konstruktormethode aufzurufen.|  
|[NewStringWithLength-Methode](icordebugeval2-newstringwithlength-method.md)|Erstellt eine neue Zeichenfolge mit der angegebenen Länge und dem angegebenen Inhalt.|  
|[RudeAbort-Methode](icordebugeval2-rudeabort-method.md)|Bricht die Berechnung ab, die von diesem `ICorDebugEval2` gerade durchgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
