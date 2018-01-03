---
title: GetWin32ResBlob-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: GetWin32ResBlob
helpviewer_keywords: GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f09bfd3ccfd3ac37854d70c226f40b17f86ccf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="ea46a-102">GetWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="ea46a-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="ea46a-103">Ruft die Win32-Ressource Blob ab.</span><span class="sxs-lookup"><span data-stu-id="ea46a-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="ea46a-104">Rufen Sie diese Methode nach dem Festlegen der Assemblyoptionen.</span><span class="sxs-lookup"><span data-stu-id="ea46a-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea46a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea46a-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ea46a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea46a-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ea46a-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ea46a-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ea46a-108">Datei-Token verwendet, um den Dateinamen verwendet werden, beim Erstellen der Win32-Versionsressource abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ea46a-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="ea46a-109">"True", wenn die Datei eine DLL für eine EXE-Datei "false" ist.</span><span class="sxs-lookup"><span data-stu-id="ea46a-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="ea46a-110">Symbol "optional" So fügen Sie die Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="ea46a-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="ea46a-111">Empfängt die Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="ea46a-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="ea46a-112">Die Größe des BLOBs empfängt.</span><span class="sxs-lookup"><span data-stu-id="ea46a-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea46a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ea46a-113">Return Value</span></span>  
 <span data-ttu-id="ea46a-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea46a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea46a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea46a-115">Requirements</span></span>  
 <span data-ttu-id="ea46a-116">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="ea46a-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea46a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea46a-117">See Also</span></span>  
 [<span data-ttu-id="ea46a-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea46a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ea46a-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea46a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ea46a-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ea46a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
