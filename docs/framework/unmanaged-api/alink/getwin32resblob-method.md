---
title: GetWin32ResBlob-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: ff3103a46390c880a56ff443bfe20744f2ba0bfd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430689"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="4ea3f-102">GetWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="4ea3f-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="4ea3f-103">Retrieves Win32 resource blob.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="4ea3f-104">Call this method after setting assembly options.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea3f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ea3f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ea3f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ea3f-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4ea3f-107">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4ea3f-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span><span class="sxs-lookup"><span data-stu-id="4ea3f-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="4ea3f-109">TRUE if file is a DLL, false for an EXE.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="4ea3f-110">Optional icon to insert into the resource blob.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="4ea3f-111">Receives the resource blob.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="4ea3f-112">Receives the size of the blob.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ea3f-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4ea3f-113">Return Value</span></span>  
 <span data-ttu-id="4ea3f-114">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="4ea3f-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ea3f-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ea3f-115">Requirements</span></span>  
 <span data-ttu-id="4ea3f-116">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="4ea3f-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea3f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ea3f-117">See also</span></span>

- [<span data-ttu-id="4ea3f-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ea3f-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4ea3f-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ea3f-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4ea3f-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4ea3f-120">ALink API</span></span>](index.md)
