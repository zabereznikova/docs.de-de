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
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095881"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="2b213-102">ICorDebugObjectValue::GetFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="2b213-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="2b213-103">Ruft den Wert des angegebenen Felds der angegebenen Klasse für diesen Objektwert ab.</span><span class="sxs-lookup"><span data-stu-id="2b213-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b213-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b213-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b213-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b213-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="2b213-106">in Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse darstellt, für die der Feldwert zu erhalten ist.</span><span class="sxs-lookup"><span data-stu-id="2b213-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="2b213-107">in Ein `mdFieldDef` Token, das auf die Metadaten verweist, die das Feld beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2b213-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="2b213-108">vorgenommen Ein Zeiger auf ein ICorDebugValue-Objekt, das den Wert des angegebenen Felds darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b213-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b213-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b213-109">Remarks</span></span>  
 <span data-ttu-id="2b213-110">Die im `pClass`-Parameter angegebene-Klasse muss sich in der Hierarchie der-Klasse des Objekt Werts befinden, und das Feld muss ein Feld dieser Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="2b213-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="2b213-111">Die `GetFieldValue`-Methode ist für generische Objekte und generische Klassen weiterhin erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2b213-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="2b213-112">Wenn z. b. MyDictionary\<V > von der Wörterbuch\<String, v > erbt und der Objektwert vom Typ MyDictionary\<Int32 > ist, wird ein Feld Wörterbuch\<Zeichenfolge, Int32 >.</span><span class="sxs-lookup"><span data-stu-id="2b213-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b213-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b213-113">Requirements</span></span>  
 <span data-ttu-id="2b213-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b213-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b213-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b213-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b213-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b213-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b213-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b213-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b213-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b213-118">See also</span></span>
