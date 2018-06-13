---
title: ICorDebugObjectValue::GetFieldValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 230666cefdadd56465fac35222500ad4b6da67e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418301"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="96544-102">ICorDebugObjectValue::GetFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="96544-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="96544-103">Ruft den Wert des angegebenen Felds der angegebenen Klasse für den Wert dieses Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="96544-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96544-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96544-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96544-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="96544-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="96544-106">[in] Ein Zeiger auf ein "ICorDebugClass"-Objekt, das die Klasse für das Abrufen des Wert des Felds darstellt.</span><span class="sxs-lookup"><span data-stu-id="96544-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="96544-107">[in] Ein `mdFieldDef` -Token, die Metadaten zum Beschreiben des Felds verweist.</span><span class="sxs-lookup"><span data-stu-id="96544-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="96544-108">[out] Ein Zeiger auf ein "ICorDebugValue"-Objekt, das den Wert des angegebenen Felds darstellt.</span><span class="sxs-lookup"><span data-stu-id="96544-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96544-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96544-109">Remarks</span></span>  
 <span data-ttu-id="96544-110">Die Klasse, angegeben der `pClass` -Parameter muss in der Hierarchie den Objektwert-Klasse, und das Feld muss ein Feld dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="96544-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="96544-111">Die `GetFieldValue` Methode ist für generische Objekte und generische Klassen dennoch erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="96544-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="96544-112">Z. B. wenn MyDictionary\<V > erbt von Wörterbuch\<"string", "V >, und der Wert des Objekts vom Typ MyDictionary\<int32 >, und übergeben Sie die `ICorDebugClass` Objekt für das Wörterbuch\<K, V > wird ein Feld des Wörterbuchs abgerufen\<String, int32 >.</span><span class="sxs-lookup"><span data-stu-id="96544-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96544-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96544-113">Requirements</span></span>  
 <span data-ttu-id="96544-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96544-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96544-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96544-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96544-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96544-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96544-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96544-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96544-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96544-118">See Also</span></span>  
    
 
