---
title: ICorDebugChain::GetStackRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce5e42bb9374f22ad29ef0e97a141a796f087a98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange-Methode
Ruft den Adressbereich des Stapelsegments für diese Kette ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pStart`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` -Wert, der die Startadresse des Stapelsegments liegt.  
  
 `pEnd`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` -Wert, der die Endadresse des Stapelsegments liegt.  
  
## <a name="remarks"></a>Hinweise  
 Die numerische Bereich ist sinnvoll, nur für den Vergleich der Stack-Frame-Speicherorte. Sie können keine Annahmen dazu was tatsächlich auf dem Stapel gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
