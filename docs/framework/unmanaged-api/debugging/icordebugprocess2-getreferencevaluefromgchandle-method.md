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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60624a5f6323399d06bda4e0280de8fbe861bd9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419584"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode
Ruft einen Verweiszeiger auf dem angegebenen verwalteten Objekt, das eine Garbagecollection-handle verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `handle`  
 [in] Ein Zeiger auf ein verwaltetes Objekt, das eine Garbage Collection-Handle verfügt. Dieser Wert ist eine <xref:System.IntPtr> Objekt abgerufen werden können, und wählen Sie die <xref:System.Runtime.InteropServices.GCHandle> für das verwaltete Objekt.  
  
 `pOutValue`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugReferenceValue-Objekts, das einen Verweis auf das angegebene verwaltete Objekt darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Verwechseln Sie nicht den Wert der zurückgegebene Verweis mit einer Garbage Collection-Verweiswert.  
  
 Der zurückgegebene Verweis verhält sich wie ein normaler Verweis. Es wird deaktiviert, wenn die Ausführung von Code nach einem Haltepunkt fortgesetzt wird. Die Lebensdauer des Zielobjekts wird von der Lebensdauer der Verweiswert nicht beeinflusst.  
  
> [!NOTE]
>  Die `GetReferenceValueFromGCHandle` Methode wird nicht überprüft, ob das Handle. Aus diesem Grund die `GetReferenceValueFromGCHandle` Methode kann möglicherweise beschädigt, des Debuggers und der Code gedebuggt wird, wenn ein ungültiges Handle übergeben wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
