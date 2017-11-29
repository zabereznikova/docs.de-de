---
title: ICorDebugFunction::GetILCode-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetILCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da955f6eb8e7480fb23192e1a77341166dd40f3b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode-Methode
Ruft die ICorDebugCode-Instanz, die die Microsoft intermediate Language (MSIL)-Code dieses ICorDebugFunction-Objekt zugeordnet darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppCode`  
 [out] Ein Zeiger auf die `ICorDebugCode` -Instanz oder null, wenn die Funktion nicht in MSIL kompiliert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Bearbeiten und Fortfahren wurde zugelassen. für diese Funktion die `GetILCode` Methode den MSIL-Code entspricht diese Funktion bearbeitete Version des Codes in der common Language Runtime (CLR) erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
