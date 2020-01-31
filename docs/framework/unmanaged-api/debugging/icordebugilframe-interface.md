---
title: ICorDebugILFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 7a27b8ec512498c7bf817aca36267c37d8070a4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788585"
---
# <a name="icordebugilframe-interface"></a>ICorDebugILFrame-Schnittstelle

Stellt einen Stapel Rahmen von MSIL-Code (Microsoft Intermediate Language) dar. Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[CanSetIP-Methode](icordebugilframe-cansetip-method.md)|Ruft einen Wert ab, der angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position festzulegen.|  
|[EnumerateArguments-Methode](icordebugilframe-enumeratearguments-method.md)|Ruft einen Enumerator für die Argumente in diesem Frame ab.|  
|[EnumerateLocalVariables-Methode](icordebugilframe-enumeratelocalvariables-method.md)|Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.|  
|[GetArgument-Methode](icordebugilframe-getargument-method.md)|Ruft den Wert des angegebenen Arguments in diesem MSIL-Stapel Rahmen ab.|  
|[GetIP-Methode](icordebugilframe-getip-method.md)|Ruft den Wert des Anweisungs Zeigers und einen bitweisen Kombinationswert ab, der beschreibt, wie der Wert des Anweisungs Zeigers abgerufen wurde.|  
|[GetLocalVariable-Methode](icordebugilframe-getlocalvariable-method.md)|Ruft den Wert der angegebenen lokalen Variablen in diesem MSIL-Stapel Rahmen ab.|  
|[GetStackDepth-Methode](icordebugilframe-getstackdepth-method.md)|Nicht implementiert.|  
|[GetStackValue-Methode](icordebugilframe-getstackvalue-method.md)|Nicht implementiert.|  
|[SetIP-Methode](icordebugilframe-setip-method.md)|Legt den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code fest.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugILFrame`-Schnittstelle ist eine spezialisierte ICorDebug-Frame-Schnittstelle. Sie wird entweder für MSIL-Code Rahmen oder for just-in-time (JIT)-kompilierte Frames verwendet. Die JIT-kompilierten Frames implementieren sowohl die `ICorDebugILFrame`-Schnittstelle als auch die ICorDebugNativeFrame-Schnittstelle.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
