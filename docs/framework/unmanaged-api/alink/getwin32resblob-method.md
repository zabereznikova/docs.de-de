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
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684511"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="0ba17-102">GetWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="0ba17-102">GetWin32ResBlob Method</span></span>

<span data-ttu-id="0ba17-103">Ruft das Win32-ressourcenblob ab.</span><span class="sxs-lookup"><span data-stu-id="0ba17-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="0ba17-104">Diese Methode nach dem Festlegen der Assemblyoptionen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0ba17-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba17-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ba17-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0ba17-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ba17-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="0ba17-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="0ba17-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0ba17-108">Datei Token, das zum Abrufen des Datei namens verwendet wird, der beim Erstellen der Win32-Versions Ressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ba17-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="0ba17-109">TRUE, wenn die Datei eine dll ist, false für eine exe-Datei.</span><span class="sxs-lookup"><span data-stu-id="0ba17-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="0ba17-110">Optionales Symbol, das in das ressourcenblob eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ba17-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="0ba17-111">Empfängt das ressourcenblob.</span><span class="sxs-lookup"><span data-stu-id="0ba17-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="0ba17-112">Empfängt die Größe des BLOBs.</span><span class="sxs-lookup"><span data-stu-id="0ba17-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ba17-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ba17-113">Return Value</span></span>  

 <span data-ttu-id="0ba17-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="0ba17-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba17-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ba17-115">Requirements</span></span>  

 <span data-ttu-id="0ba17-116">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="0ba17-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba17-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ba17-117">See also</span></span>

- [<span data-ttu-id="0ba17-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ba17-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0ba17-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ba17-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0ba17-120">ALink-API</span><span class="sxs-lookup"><span data-stu-id="0ba17-120">ALink API</span></span>](index.md)
