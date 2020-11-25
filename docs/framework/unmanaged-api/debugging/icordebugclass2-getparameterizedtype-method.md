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
ms.openlocfilehash: 139181975d16c2cdacec10ed646cfc2b8fb31a20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717993"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType-Methode

Ruft die Typdeklaration für diese Klasse ab.  
  
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
 in Ein Wert der CorElementType-Enumeration, der den Elementtyp für diese Klasse angibt: Legen Sie diesen Wert auf ELEMENT_TYPE_VALUETYPE fest, wenn dieses ICorDebugClass2 einen Werttyp darstellt. Legen Sie diesen Wert auf ELEMENT_TYPE_CLASS fest, wenn dieser `ICorDebugClass2` einen komplexen Typ darstellt.  
  
 `nTypeArgs`  
 in Die Anzahl der Typparameter, wenn der Typ generisch ist. Die Anzahl der Typparameter (sofern vorhanden) muss mit der von der Klasse benötigten Anzahl identisch sein.  
  
 `ppTypeArgs`  
 in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das einen Typparameter darstellt. Wenn die Klasse nicht generisch ist, ist dieser Wert NULL.  
  
 `ppType`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das die Typdeklaration darstellt. Dieses Objekt entspricht einem- <xref:System.Type> Objekt in verwaltetem Code.  
  
## <a name="remarks"></a>Hinweise  

 Wenn die Klasse nicht generisch ist, d. h., wenn Sie keine Typparameter aufweist, ruft `GetParameterizedType` einfach das Lauf Zeit Typen Objekt ab, das der-Klasse entspricht. Der- `elementType` Parameter sollte auf den richtigen Elementtyp für die-Klasse festgelegt werden: ELEMENT_TYPE_VALUETYPE, wenn die Klasse ein Werttyp ist, andernfalls ELEMENT_TYPE_CLASS.  
  
 Wenn die Klasse Typparameter akzeptiert (z. b `ArrayList<T>` .), können Sie verwenden, `GetParameterizedType` um ein Typobjekt für einen instanziierten Typ wie zu erstellen `ArrayList<int>` .  
  
## <a name="background-information"></a>Hintergrundinformationen  

 In den .NET Framework Versionen 1,0 und 1,1 kann jeder Typ in den Metadaten direkt einem Typ im laufenden Prozess zugeordnet werden. Folglich verfügten ein Metadatentyp und ein Lauf Zeittyp im laufenden Prozess über eine einzelne Darstellung. Allerdings kann ein generischer Typ in Metadaten vielen unterschiedlichen Instanziierungen des Typs im laufenden Prozess zugeordnet werden. Beispielsweise kann der Metadatentyp `SortedList<K,V>` `SortedList<String, EmployeeRecord>` , `SortedList<Int32, String>` , `SortedList<String,Array<Int32>>` usw. zugeordnet werden. Daher benötigen Sie eine Möglichkeit, die Typinstanziierung zu verarbeiten.  
  
 In der .NET Framework Version 2,0 wird die- `ICorDebugType` Schnittstelle eingeführt. Bei einem generischen Typ `ICorDebugClass` stellt ein `ICorDebugClass2` -oder-Objekt den nicht instanziierten Typ ( `SortedList<K,V>` ) dar, und ein- `ICorDebugType` Objekt stellt die verschiedenen instanziierten Typen dar. Wenn Sie ein- `ICorDebugClass` oder- `ICorDebugClass2` Objekt haben, können Sie ein- `ICorDebugType` Objekt für jede Instanziierung erstellen, indem Sie die- `ICorDebugClass2::GetParameterizedType` Methode aufrufen. Sie können auch ein- `ICorDebugType` Objekt für einen einfachen Typ erstellen, z. b. Int32, oder für einen nicht generischen Typ.  
  
 Die Einführung des- `ICorDebugType` Objekts zur Darstellung der Lauf Zeit Darstellung eines Typs wirkt sich in der gesamten API auf einen Ripple-Effekt aus. Funktionen, die zuvor ein- `ICorDebugClass` oder- `ICorDebugClass2` Objekt oder sogar einen-Wert übernommen haben `CorElementType` , werden verallgemeinert, um ein- `ICorDebugType` Objekt  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
