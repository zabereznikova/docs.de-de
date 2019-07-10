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
ms.openlocfilehash: 825bb945e0d8662a4dadc9d688de6a677165df4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741470"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="798a2-102">SetManifestFile-Methode</span><span class="sxs-lookup"><span data-stu-id="798a2-102">SetManifestFile Method</span></span>
<span data-ttu-id="798a2-103">Können Sie angeben oder Zurücksetzen der Manifestdatei, die der Linker beim Erstellen der Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="798a2-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="798a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="798a2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="798a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="798a2-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="798a2-106">Der Name der Manifestdatei, deren Inhalt in der Win32-Ressourcen-Blob abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="798a2-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="798a2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="798a2-107">Return Value</span></span>  
 <span data-ttu-id="798a2-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="798a2-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="798a2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="798a2-109">Remarks</span></span>  
 <span data-ttu-id="798a2-110">Rufen Sie diese, bevor Sie die Win32ResBlob aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="798a2-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="798a2-111">Der Wert des der `pszFile` Parameter ist der Name der Manifestdatei, deren Inhalt werden gelesen und in die Win32-Ressourcen mit der ID von RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="798a2-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="798a2-112">Wenn mit einem NULL-Parameter aufgerufen, wird zuvor gelesenen Manifest gelöscht.</span><span class="sxs-lookup"><span data-stu-id="798a2-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="798a2-113">Dies ermöglicht Ihnen, den Status des Linkers der Initialisierungszeit zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="798a2-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="798a2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="798a2-114">Requirements</span></span>  
 <span data-ttu-id="798a2-115">Erfordert aLink.h</span><span class="sxs-lookup"><span data-stu-id="798a2-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="798a2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="798a2-116">See also</span></span>

- [<span data-ttu-id="798a2-117">IALink3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798a2-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="798a2-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="798a2-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="798a2-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798a2-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="798a2-120">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="798a2-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
