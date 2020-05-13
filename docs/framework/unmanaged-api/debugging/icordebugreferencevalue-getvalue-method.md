---
title: ICorDebugReferenceValue::GetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
ms.openlocfilehash: 6417be4ab7c74d885edffad41085edca27bcf1ce
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378586"
---
# <a name="icordebugreferencevaluegetvalue-method"></a>ICorDebugReferenceValue::GetValue-Methode
Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pValue`  
 vorgenommen Ein Zeiger auf einen- `CORDB_ADDRESS` Wert, der die Adresse des Objekts angibt, auf das dieses ICorDebugReferenceValue-Objekt verweist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
