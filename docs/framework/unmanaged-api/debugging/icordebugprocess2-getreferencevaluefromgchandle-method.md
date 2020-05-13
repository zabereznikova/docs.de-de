---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: 143eefd557511f80007c88c1678143a885377467
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212983"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode
Ruft einen Verweis Zeiger auf das angegebene verwaltete Objekt ab, das über ein Garbage Collection Handle verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `handle`  
 in Ein Zeiger auf ein verwaltetes Objekt, das über ein Garbage Collection Handle verfügt. Dieser Wert ist ein <xref:System.IntPtr> -Objekt und kann vom <xref:System.Runtime.InteropServices.GCHandle> für das verwaltete Objekt abgerufen werden.  
  
 `pOutValue`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugReferenceValue-Objekts, das einen Verweis auf das angegebene verwaltete Objekt darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Verwechseln Sie den zurückgegebenen Verweis Wert nicht mit einem Garbage Collection Verweis Wert.  
  
 Der zurückgegebene Verweis verhält sich wie ein normaler Verweis. Diese Option ist deaktiviert, wenn die Codeausführung nach einem Breakpoint fortgesetzt wird. Die Lebensdauer des Zielobjekts wird von der Lebensdauer des Verweis Werts nicht beeinträchtigt.  
  
> [!NOTE]
> Die- `GetReferenceValueFromGCHandle` Methode validiert das Handle nicht. Daher kann die `GetReferenceValueFromGCHandle` -Methode den Debugger und den Code, der debuggt wird, potenziell beschädigen, wenn ein ungültiges Handle übermittelt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
