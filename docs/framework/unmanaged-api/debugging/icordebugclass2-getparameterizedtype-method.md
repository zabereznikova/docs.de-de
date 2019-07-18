---
title: ICorDebugClass2::GetParameterizedType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bfc503bfc2b278d7a7344b94cb089cd8e019890
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747767"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType-Methode
Ruft die Deklaration des Typs für diese Klasse ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `elementType`  
 [in] Ein Wert, der CorElementType-Enumeration, die angibt, den Typ des Elements, für diese Klasse: Legen Sie diesen Wert auf ELEMENT_TYPE_VALUETYPE, wenn diese ICorDebugClass2 einen Werttyp darstellt. Legen Sie diesen Wert auf ELEMENT_TYPE_CLASS, wenn diese `ICorDebugClass2` stellt einen komplexen Typ dar.  
  
 `nTypeArgs`  
 [in] Die Anzahl von Typparametern, wenn der Typ generisch ist. Die Anzahl der Parameter vom Typ (sofern vorhanden) muss es sich um die Anzahl, die erforderlich sind, von der Klasse übereinstimmen.  
  
 `ppTypeArgs`  
 [in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugType-Objekt verweist, die einen Typparameter darstellt. Wenn die Klasse nicht generisch ist, ist dieser Wert null.  
  
 `ppType`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugType` Objekt, das die Deklaration des Typs darstellt. Dieses Objekt entspricht einem <xref:System.Type> Objekt in verwaltetem Code.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Klasse nicht generisch, wenn es keine Typparameter aufweist, also ist `GetParameterizedType` ruft einfach die Runtime-Typ-Objekt für die Klasse ab. Die `elementType` Parameter sollte auf den richtigen Elementtyp für die Klasse festgelegt werden: ELEMENT_TYPE_VALUETYPE, wenn die Klasse ein Werttyp ist; andernfalls ELEMENT_TYPE_CLASS.  
  
 Wenn die Klasse die Typparameter akzeptiert (z. B. `ArrayList<T>`), können Sie `GetParameterizedType` ein Typobjekt für einen instanziierten Typ erstellen, wie z. B. `ArrayList<int>`.  
  
## <a name="background-information"></a>Hintergrundinformationen  
 In der .NET Framework-Versionen 1.0 und 1.1 kann jeden Typ in den Metadaten direkt zu einem Typ in den laufenden Prozess zugeordnet werden. Daher wurden bisher ein Metadatentyp und einen Laufzeittyp eine einzelne Darstellung der ausgeführte Prozess. Ein generischer Typ in den Metadaten kann jedoch viele verschiedene Instanziierungen eines Typs in den laufenden Prozess zugeordnet werden. Z. B. der Metadatentyp `SortedList<K,V>` können zuordnen `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`und so weiter. Daher benötigen Sie eine Möglichkeit zum Verarbeiten von Typinstanziierung.  
  
 .NET Framework, Version 2.0 stellt die `ICorDebugType` Schnittstelle. Für einen generischen Typ ein `ICorDebugClass` oder `ICorDebugClass2` Objekt darstellt, den nicht instanziierten Typ (`SortedList<K,V>`), und ein `ICorDebugType` Objekt darstellt, die verschiedenen instanziierten. Erhält ein `ICorDebugClass` oder `ICorDebugClass2` -Objekt verwenden, können Sie erstellen eine `ICorDebugType` -Objekt für jede Instanziierung durch Aufrufen der `ICorDebugClass2::GetParameterizedType` Methode. Sie können auch erstellen, eine `ICorDebugType` Objekt für einen einfachen Typ, z. B. Int32, oder für einen nichtgenerischen Typ.  
  
 Die Einführung der `ICorDebugType` Objekt zur Darstellung der Laufzeit-Konzept eines Typs hat einen Welleneffekt, in der API. Funktionen, die zuvor hat eine `ICorDebugClass` oder `ICorDebugClass2` Objekt oder sogar eine `CorElementType` Wert generalisiert werden, wird ein `ICorDebugType` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
