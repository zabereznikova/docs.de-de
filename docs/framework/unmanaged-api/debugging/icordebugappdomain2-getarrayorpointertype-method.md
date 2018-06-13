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
ms.openlocfilehash: cb3f0ca6d930b22f30fe9bbc5b5a04bf1e034f34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405824"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>ICorDebugAppDomain2::GetArrayOrPointerType-Methode
Ruft ein Array des angegebenen Typs oder ein Zeiger oder Verweis auf den angegebenen Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `elementType`  
 [in] Der Wert der CorElementType-Enumeration, die angibt, die zugrunde liegenden systemeigenen Typ (ein Array, Zeiger oder Verweis) erstellt werden soll.  
  
 `nRank`  
 [in] Der Rang (d. h. die Anzahl der Dimensionen) des Arrays. Dieser Wert muss 0 sein, wenn `elementType` gibt einen Zeiger oder Verweis Typ an.  
  
 `pTypeArg`  
 [in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des Arrays darstellt, Zeiger oder Verweis erstellt werden soll.  
  
 `ppType`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugType` geben Objekt, das die konstruierte Array, Zeigertyp oder Verweis darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der *ElementType* muss eines der folgenden sein:  
  
-   ELEMENT_TYPE_PTR  
  
-   ELEMENT_TYPE_BYREF  
  
-   Einem oder ELEMENT_TYPE_SZARRAY  
  
 Wenn der Wert der *ElementType* ELEMENT_TYPE_PTR oder ELEMENT_TYPE_BYREF, *nRank* muss 0 (null) sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
