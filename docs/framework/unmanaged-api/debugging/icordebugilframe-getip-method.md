---
title: ICorDebugILFrame::GetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd421d705a96778159cb80ad92d9ac654e88985f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP-Methode
Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pnOffset`  
 [out] Der Wert des Anweisungszeigers.  
  
 `pMappingResult`  
 [out] Ein Zeiger auf eine bitweise Kombination der CorDebugMappingResult-Enumerationswerte, die beschreiben, wie der Wert des Anweisungszeigers abgerufen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des Anweisungszeigers ist der Stapelrahmen Offset der Funktion Microsoft intermediate Language (MSIL)-Code. Wenn der Stapelrahmen aktiv ist, ist diese Adresse die nächste Anweisung ausgeführt. Wenn der Stapelrahmen nicht aktiv ist, wird diese Adresse die nächste Anweisung ausführen, wenn der Stapelrahmen erneut aktiviert wird.  
  
 Wenn dieser Rahmen eine just-in-Time (JIT) kompilierten Rahmen ist, wird der Wert des Anweisungszeigers durch Zuordnen rückwärts von den tatsächlichen systemeigenen Anweisungszeiger, daher ist der Wert möglicherweise nur ungefähre bestimmt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
