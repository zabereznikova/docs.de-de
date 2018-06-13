---
title: ICorDebugStringValue::GetString-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d3df561a3b48a4b26426235455ef1a074512f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417961"
---
# <a name="icordebugstringvaluegetstring-method"></a>ICorDebugStringValue::GetString-Methode
Ruft die Zeichenfolge, die durch ICorDebugStringValue verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cchString`  
 [in] Die Größe des `szString`-Arrays.  
  
 `pcchString`  
 [out] Ein Zeiger auf die Anzahl der Zeichen zurückgegeben, die der `szString` Array.  
  
 `szString`  
 [out] Ein Array, das die abgerufene Zeichenfolge speichert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
