---
title: ICorDebugAssembly::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
ms.openlocfilehash: daf5319f5d57f44cb20ce9f28d3c7b84c7015ff6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894918"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="0ae83-102">ICorDebugAssembly::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="0ae83-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="0ae83-103">Ruft den Namen der Assembly ab, die `ICorDebugAssembly` diese Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ae83-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ae83-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ae83-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ae83-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0ae83-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0ae83-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0ae83-107">vorgenommen Ein Zeiger auf eine ganze Zahl, die die tatsächliche Länge des Namens angibt.</span><span class="sxs-lookup"><span data-stu-id="0ae83-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="0ae83-108">vorgenommen Ein Array, in dem der Name gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="0ae83-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ae83-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ae83-109">Remarks</span></span>  
 <span data-ttu-id="0ae83-110">Die `GetName` -Methode gibt den vollständigen Pfad und den Dateinamen der Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="0ae83-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae83-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ae83-111">Requirements</span></span>  
 <span data-ttu-id="0ae83-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae83-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae83-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ae83-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ae83-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ae83-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ae83-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae83-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
