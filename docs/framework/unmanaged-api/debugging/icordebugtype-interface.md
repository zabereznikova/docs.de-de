---
title: ICorDebugType-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 9407dda7aab337f667cd5043b562d0eac94f0f04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711922"
---
# <a name="icordebugtype-interface"></a>ICorDebugType-Schnittstelle

Stellt einen Typ dar, entweder "Basic" oder "Complex" (d. h. Benutzer definiert). Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumerateTypeParameters-Methode](icordebugtype-enumeratetypeparameters-method.md)|Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die auf die generischen <xref:System.Type> Parameter der Klasse verweist, auf die von verwiesen wird `ICorDebugType` .|  
|[GetBase-Methode](icordebugtype-getbase-method.md)|Ruft einen Schnittstellen Zeiger auf einen-Wert ab, der auf `ICorDebugType` die Basisklasse der Klasse verweist, auf die diese verweist `ICorDebugType` , sofern vorhanden.|  
|[GetClass-Methode](icordebugtype-getclass-method.md)|Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die auf den typisierten Konstruktor von verweist `ICorDebugType` .|  
|[GetFirstTypeParameter-Methode](icordebugtype-getfirsttypeparameter-method.md)|Ruft einen Schnittstellen Zeiger auf einen ab, der auf `ICorDebugType` den ersten generischen <xref:System.Type> Parameter für den Konstruktor der Klasse verweist, auf die von verwiesen wird `ICorDebugType` .|  
|[GetRank-Methode](icordebugtype-getrank-method.md)|Ruft die Anzahl der Dimensionen in einem Arraytyp ab.|  
|[GetStaticFieldValue-Methode](icordebugtype-getstaticfieldvalue-method.md)|Ruft einen Schnittstellen Zeiger auf einen ICorDebugValue ab, der den Wert des statischen Felds enthält, auf das durch das angegebene Feld Token im angegebenen Stapel Rahmen verwiesen wird.|  
|[GetType-Methode](icordebugtype-gettype-method.md)|Ruft einen korelementtype-Wert ab, der den systemeigenen Typ des Common Language Runtime beschreibt, <xref:System.Type> auf den von diesem verwiesen wird `ICorDebugType` .|  
  
## <a name="remarks"></a>Hinweise  

 Wenn der Typ generisch ist, `ICorDebugClass` stellt den nicht instanziierten Typ dar. Die- `ICorDebugType` Schnittstelle stellt einen instanziierten generischen Typ dar. Hash Tabellen \<K, V> werden z. b. durch dargestellt `ICorDebugClass` , wohingegen Hashtable \<Int32, String> durch dargestellt wird `ICorDebugType` .  
  
 Nicht generische Typen werden sowohl von `ICorDebugClass` als auch von dargestellt `ICorDebugType` . Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
