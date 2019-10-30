---
title: ICorDebugILFrame2::EnumerateTypeParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 715ff5d4a06b53361d550f04e5154023d0b641bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095120"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="d91a2-102">ICorDebugILFrame2::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="d91a2-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="d91a2-103">Ruft ein ICorDebugTypeEnum-Objekt ab, das die <xref:System.Type> Parameter in diesem Frame enthält.</span><span class="sxs-lookup"><span data-stu-id="d91a2-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d91a2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d91a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d91a2-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="d91a2-106">Ein Zeiger auf die Adresse eines ICorDebugTypeEnum-Schnittstellen Objekts, das die Enumeration von Typparametern zulässt.</span><span class="sxs-lookup"><span data-stu-id="d91a2-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="d91a2-107">Die Liste der Typparameter enthält die Klassentyp Parameter (sofern vorhanden), gefolgt von den Methodentypparametern (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="d91a2-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d91a2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d91a2-108">Remarks</span></span>  
 <span data-ttu-id="d91a2-109">Verwenden Sie die [IMetaDataImport2:: enumgenericparameams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) -Methode, um zu bestimmen, wie viele Typparameter und Methodentypparameter in dieser Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d91a2-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="d91a2-110">Die Typparameter sind nicht immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d91a2-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d91a2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d91a2-111">Requirements</span></span>  
 <span data-ttu-id="d91a2-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d91a2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d91a2-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d91a2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d91a2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d91a2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d91a2-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d91a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
