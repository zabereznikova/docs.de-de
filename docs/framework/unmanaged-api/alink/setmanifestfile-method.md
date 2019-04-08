---
title: SetManifestFile-Methode
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8307960166cfc668a577431d688c439f0f794be2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072427"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="1c22e-102">SetManifestFile-Methode</span><span class="sxs-lookup"><span data-stu-id="1c22e-102">SetManifestFile Method</span></span>
<span data-ttu-id="1c22e-103">Können Sie angeben oder Zurücksetzen der Manifestdatei, die der Linker beim Erstellen der Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c22e-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c22e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c22e-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c22e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c22e-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="1c22e-106">Der Name der Manifestdatei, deren Inhalt in der Win32-Ressourcen-Blob abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1c22e-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c22e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1c22e-107">Return Value</span></span>  
 <span data-ttu-id="1c22e-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="1c22e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c22e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c22e-109">Remarks</span></span>  
 <span data-ttu-id="1c22e-110">Rufen Sie diese, bevor Sie die Win32ResBlob aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1c22e-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="1c22e-111">Der Wert des der `pszFile` Parameter ist der Name der Manifestdatei, deren Inhalt werden gelesen und in die Win32-Ressourcen mit der ID von RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="1c22e-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="1c22e-112">Wenn mit einem NULL-Parameter aufgerufen, wird zuvor gelesenen Manifest gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1c22e-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="1c22e-113">Dies ermöglicht Ihnen, den Status des Linkers der Initialisierungszeit zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1c22e-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c22e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c22e-114">Requirements</span></span>  
 <span data-ttu-id="1c22e-115">Erfordert aLink.h</span><span class="sxs-lookup"><span data-stu-id="1c22e-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c22e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c22e-116">See also</span></span>

- [<span data-ttu-id="1c22e-117">IALink3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c22e-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="1c22e-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="1c22e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="1c22e-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c22e-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1c22e-120">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="1c22e-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
