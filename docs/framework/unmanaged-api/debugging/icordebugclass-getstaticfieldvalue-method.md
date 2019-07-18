---
title: ICorDebugClass::GetStaticFieldValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7649d91ca2b654952d1d5ab0d45f7903d3c46a32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745543"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>ICorDebugClass::GetStaticFieldValue-Methode
Ruft den Wert des angegebenen statischen Felds ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fieldDef`  
 [in] Ein Feld `Def` -Token, verweist das Feld abgerufen werden sollen.  
  
 `pFrame`  
 [in] Ein Zeiger auf ein ICorDebugFrame-Objekt, das den Rahmen verwendet werden, um Mehrdeutigkeiten zwischen Thread oder Kontext Anwendung Mehrdeutigkeit aufzulösen darstellt.  
  
 Wenn das statische Feld relativ zu einem Thread, einen Kontext oder eine Anwendungsdomäne ist, wird der Frame den richtigen Wert bestimmen.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des statischen Felds darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Für parametrisierte Typen bezieht die bestimmten Instanziierung der Wert eines statischen Felds. Aus diesem Grund, wenn der Konstruktor der Klasse Parameter des Typs <xref:System.Type>, rufen Sie [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) anstelle von `ICorDebugClass::GetStaticFieldValue`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
