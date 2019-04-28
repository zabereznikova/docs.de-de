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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789791"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="78445-102">GetWin32ResBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="78445-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="78445-103">Ruft die Win32-Ressourcen-Blob ab.</span><span class="sxs-lookup"><span data-stu-id="78445-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="78445-104">Rufen Sie diese Methode nach dem Festlegen von Assemblyoptionen für die an.</span><span class="sxs-lookup"><span data-stu-id="78445-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78445-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="78445-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="78445-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="78445-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="78445-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="78445-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="78445-108">Datei-Token verwendet, um den Namen der Datei, die beim Erstellen der Versionsressource der Win32-verwendet werden</span><span class="sxs-lookup"><span data-stu-id="78445-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="78445-109">TRUE, wenn die Datei eine DLL, eine EXE-Datei "false" ist.</span><span class="sxs-lookup"><span data-stu-id="78445-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="78445-110">Symbol "optional" zum Einfügen in das Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="78445-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="78445-111">Empfängt die Ressourcen-Blob.</span><span class="sxs-lookup"><span data-stu-id="78445-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="78445-112">Empfängt die Größe des BLOBs.</span><span class="sxs-lookup"><span data-stu-id="78445-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78445-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="78445-113">Return Value</span></span>  
 <span data-ttu-id="78445-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="78445-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78445-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78445-115">Requirements</span></span>  
 <span data-ttu-id="78445-116">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="78445-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78445-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78445-117">See also</span></span>

- [<span data-ttu-id="78445-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78445-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="78445-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78445-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="78445-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="78445-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
