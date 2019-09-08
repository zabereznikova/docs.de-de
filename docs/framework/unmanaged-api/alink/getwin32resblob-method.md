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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b26f08548ac964fae2f4d64db50167add327eb2d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777368"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="a10a7-102">GetWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="a10a7-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="a10a7-103">Ruft das Win32-ressourcenblob ab.</span><span class="sxs-lookup"><span data-stu-id="a10a7-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="a10a7-104">Diese Methode nach dem Festlegen der Assemblyoptionen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a10a7-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a10a7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a10a7-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a10a7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a10a7-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a10a7-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="a10a7-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a10a7-108">Datei Token, das zum Abrufen des Datei namens verwendet wird, der beim Erstellen der Win32-Versions Ressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a10a7-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="a10a7-109">TRUE, wenn die Datei eine dll ist, false für eine exe-Datei.</span><span class="sxs-lookup"><span data-stu-id="a10a7-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="a10a7-110">Optionales Symbol, das in das ressourcenblob eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a10a7-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="a10a7-111">Empfängt das ressourcenblob.</span><span class="sxs-lookup"><span data-stu-id="a10a7-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="a10a7-112">Empfängt die Größe des BLOBs.</span><span class="sxs-lookup"><span data-stu-id="a10a7-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a10a7-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a10a7-113">Return Value</span></span>  
 <span data-ttu-id="a10a7-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a10a7-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a10a7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a10a7-115">Requirements</span></span>  
 <span data-ttu-id="a10a7-116">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="a10a7-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a10a7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a10a7-117">See also</span></span>

- [<span data-ttu-id="a10a7-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a10a7-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a10a7-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a10a7-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a10a7-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a10a7-120">ALink API</span></span>](index.md)
