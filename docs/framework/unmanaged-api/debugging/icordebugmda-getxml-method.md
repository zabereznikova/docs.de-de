---
title: ICorDebugMDA::GetXML-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: 9a088c7e4e9c72c8247ccdd384bc724587210c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710869"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="00d5c-102">ICorDebugMDA::GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="00d5c-102">ICorDebugMDA::GetXML Method</span></span>

<span data-ttu-id="00d5c-103">Ruft den vollständigen XML-Stream ab, der dem von [ICorDebugMDA](icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="00d5c-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d5c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00d5c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00d5c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00d5c-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="00d5c-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="00d5c-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="00d5c-107">vorgenommen Ein Zeiger auf die Länge des XML-Streams.</span><span class="sxs-lookup"><span data-stu-id="00d5c-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="00d5c-108">vorgenommen Ein Array, in dem der XML-Stream gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="00d5c-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="00d5c-109">Das Array ist möglicherweise leer.</span><span class="sxs-lookup"><span data-stu-id="00d5c-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00d5c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00d5c-110">Remarks</span></span>  

 <span data-ttu-id="00d5c-111">`GetXML`Abhängig von der Größe des zugeordneten XML-Streams kann sich die-Methode potenziell auf die Leistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="00d5c-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00d5c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="00d5c-112">Requirements</span></span>  

 <span data-ttu-id="00d5c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00d5c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00d5c-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00d5c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00d5c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00d5c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00d5c-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00d5c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d5c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00d5c-117">See also</span></span>

- [<span data-ttu-id="00d5c-118">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00d5c-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="00d5c-119">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="00d5c-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
