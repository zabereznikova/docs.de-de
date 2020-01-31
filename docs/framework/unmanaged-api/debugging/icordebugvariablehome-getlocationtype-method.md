---
title: 'Icordebugvariablehome:: getlocationtype-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 5d33c917ab814083ec2f3a3f3de6bdc264d90b77
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791007"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="7f0dc-102">Icordebugvariablehome:: getlocationtype-Methode</span><span class="sxs-lookup"><span data-stu-id="7f0dc-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="7f0dc-103">Ruft den Typ des systemeigenen Speicher Orts der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="7f0dc-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f0dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f0dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f0dc-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7f0dc-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="7f0dc-106">vorgenommen Ein Zeiger auf den Typ des nativen Speicher Orts der Variablen.</span><span class="sxs-lookup"><span data-stu-id="7f0dc-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="7f0dc-107">Weitere Informationen finden Sie in der [variablelocationtype](variablelocationtype-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7f0dc-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f0dc-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f0dc-108">Requirements</span></span>  
 <span data-ttu-id="7f0dc-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f0dc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f0dc-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f0dc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f0dc-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f0dc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f0dc-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f0dc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f0dc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f0dc-113">See also</span></span>

- [<span data-ttu-id="7f0dc-114">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f0dc-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="7f0dc-115">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7f0dc-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
