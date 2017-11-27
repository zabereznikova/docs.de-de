---
title: ICorDebugILFrame Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame
helpviewer_keywords: ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8d370fa971f698eb694127c72ff96499b85143d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe-interface1"></a>ICorDebugILFrame Schnittstelle1
Stellt einen Stapelrahmen von Microsoft intermediate Language (MSIL)-Code dar. Diese Schnittstelle ist eine Unterklasse von ICorDebugFrame-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanSetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Ruft einen Wert, der angibt, ob den Anweisungszeiger am angegebenen Offset Speicherort festgelegt werden kann.|  
|[EnumerateArguments-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Ruft einen Enumerator für die Argumente in diesem Frame ab.|  
|[EnumerateLocalVariables-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.|  
|[GetArgument-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Ruft den Wert des angegebenen Arguments in MSIL-Stapelrahmen ab.|  
|[GetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.|  
|[GetLocalVariable-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Ruft den Wert der angegebenen lokalen Variablen in MSIL-Stapelrahmen ab.|  
|[GetStackDepth-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Nicht implementiert.|  
|[GetStackValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Nicht implementiert.|  
|[SetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Legt den Anweisungszeiger auf die angegebene Offsetposition im MSIL-Code fest.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugILFrame` Schnittstelle ist eine spezielle ICorDebugFrame-Schnittstelle. Es dient für Rahmen der MSIL-Code oder für Just-in-Time (JIT) kompilierten Frames. Die JIT-kompilierten Rahmen implementieren sowohl die `ICorDebugILFrame` Schnittstelle und die ICorDebugNativeFrame-Schnittstelle.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
