---
title: ICorDebugILFrame-Schnittstelle1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73cf7f26b228fa5aa458a6de312df3bf777e0206
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580511"
---
# <a name="icordebugilframe-interface1"></a>ICorDebugILFrame-Schnittstelle1
Stellt einen Stapelrahmen des Microsoft intermediate Language (MSIL)-Code dar. Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanSetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Ruft einen Wert, der angibt, ob der Anweisungszeiger sich am angegebenen Offset Speicherort festgelegt werden kann.|  
|[EnumerateArguments-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Ruft einen Enumerator für die Argumente in diesem Frame ab.|  
|[EnumerateLocalVariables-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.|  
|[GetArgument-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Ruft den Wert des angegebenen Arguments in MSIL-Stapelrahmens ab.|  
|[GetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.|  
|[GetLocalVariable-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Ruft den Wert der angegebenen lokalen Variable in MSIL-Stapelrahmens ab.|  
|[GetStackDepth-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Nicht implementiert.|  
|[GetStackValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Nicht implementiert.|  
|[SetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Legt den Anweisungszeiger am angegebenen Offset Speicherort in den MSIL-Code fest.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugILFrame` Schnittstelle ist eine spezielle ICorDebugFrame-Schnittstelle. Hiermit wird für die MSIL-Code-Frames oder für die just-in-Time (JIT) kompiliert Frames. Der JIT-kompilierten Rahmen implementieren sowohl die `ICorDebugILFrame` und die ICorDebugNativeFrame-Schnittstelle.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
