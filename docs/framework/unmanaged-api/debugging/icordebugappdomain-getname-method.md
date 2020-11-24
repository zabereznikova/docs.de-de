---
title: ICorDebugAppDomain::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 501a4543940437bfe2a6cb0952aed8184107150c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672161"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="3af2e-102">ICorDebugAppDomain::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="3af2e-102">ICorDebugAppDomain::GetName Method</span></span>

<span data-ttu-id="3af2e-103">Ruft den Namen der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="3af2e-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af2e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3af2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3af2e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3af2e-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="3af2e-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="3af2e-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="3af2e-107">Legen Sie diesen Wert auf NULL fest, um diese Methode in den Abfrage Modus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="3af2e-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3af2e-108">vorgenommen Ein Zeiger auf die Größe des Namens oder die Anzahl von Zeichen, die tatsächlich in zurückgegeben werden `szName` .</span><span class="sxs-lookup"><span data-stu-id="3af2e-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="3af2e-109">Im Abfrage Modus kann der Aufrufer mit diesem Wert ermitteln, wie groß ein Puffer ist, der für den Namen zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="3af2e-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="3af2e-110">vorgenommen Ein Array, in dem der Name der Anwendungsdomäne gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3af2e-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3af2e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3af2e-111">Remarks</span></span>  

 <span data-ttu-id="3af2e-112">Ein Debugger ruft die- `GetName` Methode einmal auf, um die Größe eines Puffers zu erhalten, der für den Namen benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="3af2e-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="3af2e-113">Der-Debugger ordnet den Puffer zu und ruft dann die-Methode ein zweites Mal auf, um den Puffer zu füllen.</span><span class="sxs-lookup"><span data-stu-id="3af2e-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="3af2e-114">Der erste-Befehl, um die Größe des Namens abzurufen, wird als *Abfrage Modus* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3af2e-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3af2e-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3af2e-115">Requirements</span></span>  

 <span data-ttu-id="3af2e-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3af2e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3af2e-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3af2e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3af2e-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3af2e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3af2e-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3af2e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
