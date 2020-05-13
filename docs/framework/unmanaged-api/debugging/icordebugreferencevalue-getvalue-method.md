---
title: ICorDebugReferenceValue::GetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
ms.openlocfilehash: 6417be4ab7c74d885edffad41085edca27bcf1ce
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378586"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="45177-102">ICorDebugReferenceValue::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="45177-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="45177-103">Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="45177-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45177-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45177-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45177-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45177-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="45177-106">vorgenommen Ein Zeiger auf einen- `CORDB_ADDRESS` Wert, der die Adresse des Objekts angibt, auf das dieses ICorDebugReferenceValue-Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="45177-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45177-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="45177-107">Requirements</span></span>  
 <span data-ttu-id="45177-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45177-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45177-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45177-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45177-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45177-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45177-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45177-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
