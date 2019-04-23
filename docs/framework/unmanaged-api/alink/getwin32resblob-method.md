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
ms.openlocfilehash: a4c77ade46d2401e2499a94504808efd94f79f93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152151"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="01c0c-102">GetWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="01c0c-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="01c0c-103">Ruft die Win32-Ressourcen-Blob ab.</span><span class="sxs-lookup"><span data-stu-id="01c0c-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="01c0c-104">Rufen Sie diese Methode nach dem Festlegen von Assemblyoptionen für die an.</span><span class="sxs-lookup"><span data-stu-id="01c0c-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c0c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="01c0c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="01c0c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="01c0c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="01c0c-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="01c0c-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="01c0c-108">Datei-Token verwendet, um den Namen der Datei, die beim Erstellen der Versionsressource der Win32-verwendet werden</span><span class="sxs-lookup"><span data-stu-id="01c0c-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="01c0c-109">TRUE, wenn die Datei eine DLL, eine EXE-Datei "false" ist.</span><span class="sxs-lookup"><span data-stu-id="01c0c-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="01c0c-110">Symbol "optional" zum Einfügen in das Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="01c0c-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="01c0c-111">Empfängt die Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="01c0c-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="01c0c-112">Empfängt die Größe des BLOBs.</span><span class="sxs-lookup"><span data-stu-id="01c0c-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01c0c-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="01c0c-113">Return Value</span></span>  
 <span data-ttu-id="01c0c-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="01c0c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01c0c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01c0c-115">Requirements</span></span>  
 <span data-ttu-id="01c0c-116">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="01c0c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c0c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01c0c-117">See also</span></span>

- [<span data-ttu-id="01c0c-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01c0c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="01c0c-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01c0c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="01c0c-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="01c0c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
