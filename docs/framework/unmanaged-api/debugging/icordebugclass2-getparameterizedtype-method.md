---
title: ICorDebugClass2::GetParameterizedType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.GetParameterizedType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9cbb755bd8f52482f7eece6e9d236f29cadc419
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType-Methode
Ruft die Typdeklaration für diese Klasse ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `elementType`  
 [in] Ein Wert, der CorElementType-Enumeration, der den Elementtyp für diese Klasse angibt: Legen Sie diesen Wert auf ELEMENT_TYPE_VALUETYPE fest, wenn ICorDebugClass2 einen Wert darstellt. Legen Sie diesen Wert auf ELEMENT_TYPE_CLASS fest, wenn diese `ICorDebugClass2` stellt einen komplexen Typ dar.  
  
 `nTypeArgs`  
 [in] Die Anzahl von Typparametern, wenn der Typ generisch ist. Die Anzahl der Typparameter (sofern vorhanden) muss von der Klasse erforderliche Anzahl übereinstimmen.  
  
 `ppTypeArgs`  
 [in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die einen Typparameter darstellt. Wenn die Klasse nicht generisch ist, ist dieser Wert null.  
  
 `ppType`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das die Typdeklaration darstellt. Dieses Objekt entspricht einem <xref:System.Type> Objekt in verwaltetem Code.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Klasse nicht-generische, d. h. wenn es sich um keine Typparameter aufweist `GetParameterizedType` einfach ruft der Klasse entsprechende Common Language Runtime-Typ-Objekt. Die `elementType` Parameter sollte in den richtigen Elementtyp für die Klasse festgelegt werden: ELEMENT_TYPE_VALUETYPE, wenn die Klasse ein Werttyp ist, andernfalls ELEMENT_TYPE_CLASS.  
  
 Wenn die Klasse Typparameter akzeptiert (z. B. `ArrayList<T>`), können Sie `GetParameterizedType` So erstellen Sie ein Objekt vom Typ für einen instanziierten Typ wie z. B. `ArrayList<int>`.  
  
## <a name="background-information"></a>Hintergrundinformationen  
 In der .NET Framework-Versionen 1.0 und 1.1 konnte jeder Typ in den Metadaten direkt zu einem Typ in den laufenden Prozess zugeordnet werden. Daher musste ein Metadatentyp und einen Laufzeittyp eine einzelne Darstellung in der ausgeführte Prozess. Allerdings kann einen generischer Typ in den Metadaten auf vielen verschiedenen Instanziierungen des Typs in der laufenden Prozess zugeordnet werden. Z. B. der Metadatentyp `SortedList<K,V>` können zuordnen `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`und so weiter. Daher benötigen Sie eine Möglichkeit zum Verarbeiten von Typinstanziierung.  
  
 .NET Framework, Version 2.0 führt die `ICorDebugType` Schnittstelle. Für einen generischen Typ ein `ICorDebugClass` oder `ICorDebugClass2` Objekt darstellt, den nicht instanziierten Typ (`SortedList<K,V>`), und ein `ICorDebugType` -Objekt stellt die verschiedenen instanziierten Typen dar. Erhält ein `ICorDebugClass` oder `ICorDebugClass2` -Objekt können Sie erstellen eine `ICorDebugType` Objekt für jede Instanziierung durch Aufrufen der `ICorDebugClass2::GetParameterizedType` Methode. Sie können auch erstellen, ein `ICorDebugType` Objekt für einen einfachen Typ, z. B. Int32, oder für einen nichtgenerischen Typ.  
  
 Die Einführung der `ICorDebugType` Objekt zur Darstellung des Begriff zur Laufzeit einen Typ hat einen Welleneffekt während der API. Funktionen, die zuvor dauerte ein `ICorDebugClass` oder `ICorDebugClass2` -Objekt oder sogar eine `CorElementType` Wert werden generalisiert, um nehmen eine `ICorDebugType` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
