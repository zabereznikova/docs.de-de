---
title: CreateVersionStringFromModule-Funktion
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
ms.openlocfilehash: 1b944034251b34350057866b2a52e63e934d72d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733346"
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="174b3-102">CreateVersionStringFromModule-Funktion</span><span class="sxs-lookup"><span data-stu-id="174b3-102">CreateVersionStringFromModule Function</span></span>

<span data-ttu-id="174b3-103">Erstellt eine Versionszeichenfolge aus einem CLR-Pfad (Common Language Runtime) in einem Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="174b3-103">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="174b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="174b3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="174b3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="174b3-105">Parameters</span></span>  

 `pidDebuggee`  
 <span data-ttu-id="174b3-106">[in] Bezeichner des Prozesses, in den die Ziel-CLR geladen wird.</span><span class="sxs-lookup"><span data-stu-id="174b3-106">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="174b3-107">[in] Vollständiger oder relativer Pfad zur im Prozess geladenen Ziel-CLR.</span><span class="sxs-lookup"><span data-stu-id="174b3-107">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="174b3-108">[out] Rückgabepuffer zum Speichern der Versionszeichenfolge für die Ziel-CLR.</span><span class="sxs-lookup"><span data-stu-id="174b3-108">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="174b3-109">[in] Größe von `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="174b3-109">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="174b3-110">[out] Länge der von `pBuffer` zurückgegebenen Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="174b3-110">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="174b3-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="174b3-111">Return Value</span></span>  

 <span data-ttu-id="174b3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="174b3-112">S_OK</span></span>  
 <span data-ttu-id="174b3-113">Die Versionszeichenfolge für die Ziel-CLR wurde erfolgreich in `pBuffer` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="174b3-113">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="174b3-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="174b3-114">E_INVALIDARG</span></span>  
 <span data-ttu-id="174b3-115">`szModuleName` ist NULL, oder `pBuffer` oder `cchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="174b3-115">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="174b3-116">`pBuffer` und `cchBuffer` müssen beide NULL oder nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="174b3-116">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="174b3-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="174b3-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="174b3-118">`pdwLength` ist größer als `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="174b3-118">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="174b3-119">Dies kann ein erwartetes Ergebnis sein, wenn Sie NULL für `pBuffer` und `cchBuffer` übergeben haben und die erforderliche Puffergröße mithilfe von `pdwLength` abgefragt haben.</span><span class="sxs-lookup"><span data-stu-id="174b3-119">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="174b3-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="174b3-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="174b3-121">`szModuleName` enthält keinen Pfad zu einer gültigen CLR im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="174b3-121">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="174b3-122">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="174b3-122">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="174b3-123">`pidDebuggee` verweist auf keinen gültigen Prozess, oder anderer Fehler,</span><span class="sxs-lookup"><span data-stu-id="174b3-123">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="174b3-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="174b3-124">Remarks</span></span>  

 <span data-ttu-id="174b3-125">Diese Funktion akzeptiert einen CLR-Prozess, der von `pidDebuggee` und einem Zeichenfolgepfad identifiziert wird, der durch `szModuleName` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="174b3-125">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="174b3-126">Die Versionszeichenfolge wird im Puffer zurückgegeben, auf den `pBuffer` zeigt.</span><span class="sxs-lookup"><span data-stu-id="174b3-126">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="174b3-127">Diese Zeichenfolge ist für den Funktionsbenutzer nicht transparent. Das heißt, gibt es keine systeminterne Bedeutung in der Versionszeichenfolge selbst.</span><span class="sxs-lookup"><span data-stu-id="174b3-127">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="174b3-128">Sie wird nur im Kontext dieser Funktion und der Funktion "| [atedebugginginterfakefromversion](createdebugginginterfacefromversion-function-for-silverlight.md)" verwendet.</span><span class="sxs-lookup"><span data-stu-id="174b3-128">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="174b3-129">Diese Funktion sollte zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="174b3-129">This function should be called twice.</span></span> <span data-ttu-id="174b3-130">Übergeben Sie beim ersten Aufruf NULL für `pBuffer` und `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="174b3-130">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="174b3-131">In diesem Fall wird die für `pBuffer` erforderliche Größe des Puffers in `pdwLength` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="174b3-131">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="174b3-132">Sie können dann die Funktion ein zweites Mal aufrufen und den Puffer in `pBuffer` und dessen Größe in `cchBuffer` übergeben.</span><span class="sxs-lookup"><span data-stu-id="174b3-132">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="174b3-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="174b3-133">Requirements</span></span>  

 <span data-ttu-id="174b3-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="174b3-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="174b3-135">**Header:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="174b3-135">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="174b3-136">**Bibliothek:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="174b3-136">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="174b3-137">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="174b3-137">**.NET Framework Versions:** 3.5 SP1</span></span>
