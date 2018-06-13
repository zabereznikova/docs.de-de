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
ms.openlocfilehash: f40b99c0a81bf0f2b622c7d23157dbb5736df1ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403291"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="704c9-102">GetWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="704c9-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="704c9-103">Ruft die Win32-Ressource Blob ab.</span><span class="sxs-lookup"><span data-stu-id="704c9-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="704c9-104">Rufen Sie diese Methode nach dem Festlegen der Assemblyoptionen.</span><span class="sxs-lookup"><span data-stu-id="704c9-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="704c9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="704c9-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="704c9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="704c9-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="704c9-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="704c9-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="704c9-108">Datei-Token verwendet, um den Dateinamen verwendet werden, beim Erstellen der Win32-Versionsressource abzurufen.</span><span class="sxs-lookup"><span data-stu-id="704c9-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="704c9-109">"True", wenn die Datei eine DLL für eine EXE-Datei "false" ist.</span><span class="sxs-lookup"><span data-stu-id="704c9-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="704c9-110">Symbol "optional" So fügen Sie die Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="704c9-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="704c9-111">Empfängt die Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="704c9-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="704c9-112">Die Größe des BLOBs empfängt.</span><span class="sxs-lookup"><span data-stu-id="704c9-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="704c9-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="704c9-113">Return Value</span></span>  
 <span data-ttu-id="704c9-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="704c9-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="704c9-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="704c9-115">Requirements</span></span>  
 <span data-ttu-id="704c9-116">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="704c9-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704c9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="704c9-117">See Also</span></span>  
 [<span data-ttu-id="704c9-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="704c9-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="704c9-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="704c9-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="704c9-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="704c9-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
