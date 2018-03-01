---
title: ICorDebugILFrame2::EnumerateTypeParameters-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9180ea68dde667ffe0dc8e15b98cb82efaa667ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="0d02c-102">ICorDebugILFrame2::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="0d02c-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="0d02c-103">Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.</span><span class="sxs-lookup"><span data-stu-id="0d02c-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d02c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d02c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d02c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d02c-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="0d02c-106">Ein Zeiger auf die Adresse des ICorDebugTypeEnum-Schnittstellenobjekts, die Enumeration von Typparametern ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0d02c-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="0d02c-107">Die Liste mit Typparametern enthalten die Klassentypparameter (sofern vorhanden) gefolgt vom die Typparameter der Methode (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="0d02c-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d02c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d02c-108">Remarks</span></span>  
 <span data-ttu-id="0d02c-109">Verwenden der [IMetaDataImport2:: EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) Methode, um zu bestimmen, wie viele Typparameter der Klasse und Methode Parameter geben Sie diese Liste enthält.</span><span class="sxs-lookup"><span data-stu-id="0d02c-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="0d02c-110">Die Typparameter sind nicht immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d02c-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d02c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d02c-111">Requirements</span></span>  
 <span data-ttu-id="0d02c-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d02c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d02c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d02c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d02c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d02c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d02c-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d02c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
