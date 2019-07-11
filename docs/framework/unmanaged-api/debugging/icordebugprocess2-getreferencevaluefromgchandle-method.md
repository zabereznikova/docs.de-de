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
ms.openlocfilehash: f38f9a3ebd88e0a5abb7a6bc8cb4026dc7d0f068
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736940"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode
Ruft einen Verweiszeiger auf das angegebene verwaltete Objekt, das eine Garbagecollection verarbeitet hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `handle`  
 [in] Ein Zeiger auf ein verwaltetes Objekt, das eine Garbage Collection-Handle verfügt. Dieser Wert ist eine <xref:System.IntPtr> Objekt abgerufen werden können, und wählen Sie die <xref:System.Runtime.InteropServices.GCHandle> für das verwaltete Objekt.  
  
 `pOutValue`  
 [out] Ein Zeiger auf die Adresse des ein ICorDebugReferenceValue-Objekt, das einen Verweis auf das angegebene verwaltete Objekt darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Verwechseln Sie nicht den Wert der zurückgegebene Verweis mit einem Garbage Collection-Verweis-Wert.  
  
 Der zurückgegebene Verweis verhält sich wie ein normaler Verweis. Es ist deaktiviert, wenn die Ausführung von Code nach einem Haltepunkt fortgesetzt. Die Lebensdauer des Zielobjekts ist von der Lebensdauer der Verweiswert nicht betroffen.  
  
> [!NOTE]
>  Die `GetReferenceValueFromGCHandle` Methode überprüft nicht das Handle. Aus diesem Grund die `GetReferenceValueFromGCHandle` Methode kann möglicherweise beschädigt, den Debugger und der Code gedebuggt wird, wenn ein ungültiges Handle übergeben wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
