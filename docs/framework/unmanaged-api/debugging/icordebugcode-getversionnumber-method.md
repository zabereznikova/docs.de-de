---
title: ICorDebugCode::GetVersionNumber-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b6fd6e8043f1c62da8994b43a9b9af45fb2e3c0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700821"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="a8947-102">ICorDebugCode::GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="a8947-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="a8947-103">Ruft die einsbasierte Zahl ab, die die Version des Codes identifiziert, den dieser "ICorDebugCode" darstellt.</span><span class="sxs-lookup"><span data-stu-id="a8947-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8947-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8947-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="a8947-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a8947-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="a8947-106">vorgenommen Ein Zeiger auf die Versionsnummer des Codes.</span><span class="sxs-lookup"><span data-stu-id="a8947-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8947-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8947-107">Remarks</span></span>

 <span data-ttu-id="a8947-108">Die Versionsnummer wird jedes Mal inkrementiert, wenn ein Edit-and-Continue-Vorgang (ENC) für den Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a8947-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8947-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8947-109">Requirements</span></span>

 <span data-ttu-id="a8947-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8947-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8947-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="a8947-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8947-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8947-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8947-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8947-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
