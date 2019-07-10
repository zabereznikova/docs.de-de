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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2e53bfb46579cc51b7ad88ef7de2b9f8d2f9390
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758769"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="c9cc7-102">ICorDebugILFrame2::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="c9cc7-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="c9cc7-103">Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.</span><span class="sxs-lookup"><span data-stu-id="c9cc7-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9cc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9cc7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9cc7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9cc7-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="c9cc7-106">Ein Zeiger auf die Adresse des ICorDebugTypeEnum-Schnittstellenobjekts, die Enumeration von Typparametern ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c9cc7-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="c9cc7-107">Die Liste der Parameter vom Typ enthalten die Klassentypparameter (sofern vorhanden) gefolgt von den Methodentypparametern (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="c9cc7-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9cc7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9cc7-108">Remarks</span></span>  
 <span data-ttu-id="c9cc7-109">Verwenden der [IMetaDataImport2:: EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) Methode, um zu bestimmen, wie viele Parameter vom Typ Klasse und Methode Parameter geben Sie diese Liste enthält.</span><span class="sxs-lookup"><span data-stu-id="c9cc7-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="c9cc7-110">Die Typparameter sind nicht immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9cc7-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9cc7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9cc7-111">Requirements</span></span>  
 <span data-ttu-id="c9cc7-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9cc7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9cc7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9cc7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9cc7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9cc7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9cc7-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9cc7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
