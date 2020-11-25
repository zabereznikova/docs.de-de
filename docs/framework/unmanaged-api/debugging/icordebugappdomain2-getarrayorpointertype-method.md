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
ms.openlocfilehash: 8b3f6ae92e39f5385bf29f8b29abbb1726136088
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724766"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>ICorDebugAppDomain2::GetArrayOrPointerType-Methode

Ruft ein Array vom angegebenen Typ oder einen Zeiger oder einen Verweis auf den angegebenen Typ ab.  
  
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
 in Ein Wert der CorElementType-Enumeration, der den zugrunde liegenden systemeigenen Typ (ein Array, einen Zeiger oder einen Verweis) angibt, der erstellt werden soll.  
  
 `nRank`  
 in Der Rang (d. h. die Anzahl der Dimensionen) des Arrays. Dieser Wert muss 0 sein, wenn `elementType` einen Zeiger oder Verweistyp angibt.  
  
 `pTypeArg`  
 in Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des zu erstellenden Arrays, Zeigers oder Verweises darstellt.  
  
 `ppType`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das das erstellte Array, den Zeigertyp oder den Verweistyp darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Der Wert von *ElementType* muss einer der folgenden sein:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY oder ELEMENT_TYPE_SZARRAY  
  
 Wenn der Wert von *ElementType* ELEMENT_TYPE_PTR oder ELEMENT_TYPE_BYREF ist, muss *nRank* NULL sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
