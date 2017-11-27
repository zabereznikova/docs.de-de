---
title: SetManifestFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink3.SetManifestFile
api_location: alink.dll
api_type: COM
f1_keywords: SetManifestFile
helpviewer_keywords: SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 807452326193d193f3bc603ebc7b74a5a0f1c281
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="90624-102">SetManifestFile-Methode</span><span class="sxs-lookup"><span data-stu-id="90624-102">SetManifestFile Method</span></span>
<span data-ttu-id="90624-103">Ermöglicht es Ihnen, festzulegen, oder setzen Sie die Manifestdatei, die vom Linker beim Erstellen der Assemblys verwendet zurück.</span><span class="sxs-lookup"><span data-stu-id="90624-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90624-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90624-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90624-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90624-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="90624-106">Der Name der Manifestdatei an, deren Inhalt in der Win32-Ressourcen-Blob gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="90624-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90624-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="90624-107">Return Value</span></span>  
 <span data-ttu-id="90624-108">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90624-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90624-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90624-109">Remarks</span></span>  
 <span data-ttu-id="90624-110">Rufen Sie diese, bevor Sie die Win32ResBlob angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="90624-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="90624-111">Der Wert, der die `pszFile` Parameter ist der Name der Manifestdatei an, deren Inhalt gelesen und in der Win32-Ressourcen mit der ID von RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="90624-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="90624-112">Bei Aufruf mit einem Parameter NULL ist zuvor gelesenen Manifest deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="90624-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="90624-113">Dies ermöglicht Ihnen, den Zustand des Linkers an der Initialisierung des zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="90624-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90624-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90624-114">Requirements</span></span>  
 <span data-ttu-id="90624-115">Erfordert aLink.h</span><span class="sxs-lookup"><span data-stu-id="90624-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90624-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90624-116">See Also</span></span>  
 [<span data-ttu-id="90624-117">IALink3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90624-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [<span data-ttu-id="90624-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="90624-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [<span data-ttu-id="90624-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90624-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="90624-120">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="90624-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
