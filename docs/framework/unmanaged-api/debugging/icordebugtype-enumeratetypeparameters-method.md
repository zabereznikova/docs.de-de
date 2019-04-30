---
title: ICorDebugType::EnumerateTypeParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8fa39a54437e60737aa052c495f58422bc0d3fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946236"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters-Methode
Ruft einen Schnittstellenzeiger auf eine ICorDebugTypeEnum, die enthält die <xref:System.Type> Parameter von der Klasse, die dieser ICorDebugType verweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppTyParEnum`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugTypeEnum` , die die Parameter des Typs enthält.  
  
## <a name="remarks"></a>Hinweise  
 Sie können `EnumerateTypeParameters` Wenn von der CorElementType-Wert zurückgegeben [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ist ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR oder ELEMENT_TYPE_FNPTR. Die Anzahl der Parameter und deren Reihenfolge hängt vom Typ aus:  
  
- ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE: Die Anzahl von Typparametern, die innerhalb der `ICorDebugTypeEnum` , dass diese Methode zurückgegeben wird, hängt die Anzahl der formalen Typparameter für die entsprechende Klasse. Wenn der Typ ist z. B. `class Dict<String,int32>`, klicken Sie dann `EnumerateTypeParameters` zurück eine `ICorDebugTypeEnum` , enthält die Objekte, die darstellen `String` und `int32` nacheinander.  
  
- ELEMENT_TYPE_FNPTR: Die Anzahl von Typparametern, die innerhalb der `ICorDebugTypeEnum` können größer als die Anzahl von Argumenten, die von der Funktion akzeptiert. Der erste Typparameter, die innerhalb der `ICorDebugTypeEnum` ist der Rückgabetyp der Funktion und die nachfolgende Typparameter werden Funktionsparameter.  
  
- ELEMENT_TYPE_ARRAY ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR: Ein Typparameter wird zurückgegeben. Wenn der Typ einen Arraytyp ist, wie z. B. `int32[]`,`EnumerateTypeParameters` gibt ein `ICorDebugTypeEnum` , enthält ein Objekt zur Darstellung `int32`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
