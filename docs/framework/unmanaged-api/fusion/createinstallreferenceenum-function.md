---
title: CreateInstallReferenceEnum-Funktion
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: f089769f854bad5d3e572e0307734e06e72ca89c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108568"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="498be-102">CreateInstallReferenceEnum-Funktion</span><span class="sxs-lookup"><span data-stu-id="498be-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="498be-103">Ruft einen Zeiger auf eine [IInstallReferenceEnum](iinstallreferenceenum-interface.md) -Instanz ab, die eine Liste der Verweise einer Anwendung auf die angegebene Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="498be-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="498be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="498be-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="498be-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="498be-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="498be-106">vorgenommen Der zurückgegebene `IInstallReferenceEnum` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="498be-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="498be-107">in Der [IAssemblyName](iassemblyname-interface.md) , der die Assembly identifiziert, für die Verweise aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="498be-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="498be-108">in Flags, die das Verhalten des Enumerators beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="498be-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="498be-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="498be-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="498be-110">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="498be-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="498be-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="498be-111">Requirements</span></span>  
 <span data-ttu-id="498be-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="498be-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="498be-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="498be-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="498be-114">**Bibliothek:** "Fusion. dll" und "mscorwert. dll".</span><span class="sxs-lookup"><span data-stu-id="498be-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="498be-115">Verwenden Sie "Fusion. dll" anstelle von "mscorwert. dll", um sicherzustellen, dass Sie die richtige Version des .NET Framework als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="498be-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="498be-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="498be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="498be-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="498be-117">See also</span></span>

- [<span data-ttu-id="498be-118">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="498be-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="498be-119">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="498be-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="498be-120">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="498be-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
