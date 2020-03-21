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
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178825"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP-Methode
Ruft den Wert des Anweisungszeigers und einen bitweisen Kombinationswert ab, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pnOffset`  
 [out] Der Wert des Anweisungszeigers.  
  
 `pMappingResult`  
 [out] Ein Zeiger auf eine bitweise Kombination der CorDebugMappingResult-Enumerationswerte, die beschreiben, wie der Wert des Anweisungszeigers abgerufen wurde.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Wert des Anweisungszeigers ist der Offset des Stapelrahmens in den MSIL-Code (Microsoft Intermediate Language) der Funktion. Wenn der Stapelrahmen aktiv ist, ist diese Adresse die nächste auszuführende Anweisung. Wenn der Stapelrahmen nicht aktiv ist, ist diese Adresse die nächste Anweisung, die ausgeführt werden muss, wenn der Stapelrahmen erneut aktiviert wird.  
  
 Wenn es sich bei diesem Frame um einen Just-in-Time-Kompilierten Frame (JIT) handelt, wird der Wert des Anweisungszeigers durch Rückwärtszuordnung vom tatsächlichen systemeigenen Anweisungszeiger bestimmt, sodass der Wert nur annähernd sein kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
