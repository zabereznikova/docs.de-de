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
ms.openlocfilehash: 4f34fdf9a0eeb47e027cc874afee5bd04f5bd9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712390"
---
# <a name="icordebugilframe-interface"></a>ICorDebugILFrame-Schnittstelle

Stellt einen Stapel Rahmen von MSIL-Code (Microsoft Intermediate Language) dar. Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
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

 Die- `ICorDebugILFrame` Schnittstelle ist eine spezialisierte ICorDebug-Frame-Schnittstelle. Sie wird entweder für MSIL-Code Rahmen oder for just-in-time (JIT)-kompilierte Frames verwendet. Die JIT-kompilierten Frames implementieren sowohl die `ICorDebugILFrame` -Schnittstelle als auch die ICorDebugNativeFrame-Schnittstelle.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
