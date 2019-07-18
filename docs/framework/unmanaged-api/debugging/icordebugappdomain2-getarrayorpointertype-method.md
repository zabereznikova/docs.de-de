---
title: ICorDebugAppDomain2::GetArrayOrPointerType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd8f71ca75a795ab86c61140eacbbcfb0a18b590
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737807"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>ICorDebugAppDomain2::GetArrayOrPointerType-Methode
Ruft ein Array von den angegebenen Typ oder ein Zeiger oder Verweis auf den angegebenen Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `elementType`  
 [in] Ein Wert, der CorElementType-Enumeration, die angibt, den zugrunde liegenden systemeigenen Typ (ein Array, Zeiger oder Verweis) erstellt werden.  
  
 `nRank`  
 [in] Der Rang (d. h. die Anzahl der Dimensionen) des Arrays. Dieser Wert muss 0 sein, wenn `elementType` gibt einen Zeiger oder Verweis-Typ.  
  
 `pTypeArg`  
 [in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des Arrays darstellt, Zeiger oder Verweis erstellt werden soll.  
  
 `ppType`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugType` geben-Objekt, das erstellte Array, Zeigertyp oder Verweis darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des *ElementType* muss eine der folgenden sein:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY oder ELEMENT_TYPE_SZARRAY  
  
 Wenn der Wert des *ElementType* ELEMENT_TYPE_PTR oder ELEMENT_TYPE_BYREF, *nRank* muss NULL sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
