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
ms.openlocfilehash: b293c30060107d18c6b609efc82c4128a73cc1c7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787210"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="b8304-102">SetManifestFile-Methode</span><span class="sxs-lookup"><span data-stu-id="b8304-102">SetManifestFile Method</span></span>
<span data-ttu-id="b8304-103">Ermöglicht es Ihnen, die Manifest-Datei anzugeben oder zurückzusetzen, die der Linker beim Erstellen der Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8304-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8304-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8304-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8304-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8304-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="b8304-106">Der Name der Manifest-Datei, deren Inhalt in das Win32-Ressourcen-BLOB eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b8304-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8304-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8304-107">Return Value</span></span>  
 <span data-ttu-id="b8304-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b8304-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8304-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8304-109">Remarks</span></span>  
 <span data-ttu-id="b8304-110">Nennen Sie dies, bevor Sie die Win32ResBlob anfordern.</span><span class="sxs-lookup"><span data-stu-id="b8304-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="b8304-111">Der Wert des `pszFile` -Parameters ist der Name der Manifest-Datei, deren Inhalt in den Win32-Ressourcen mit der ID RT_MANIFEST gelesen und abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b8304-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="b8304-112">Wenn Sie mit einem Parameter von NULL aufgerufen wird, werden alle zuvor gelesenen Manifeste gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b8304-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="b8304-113">Dadurch kann der Zustand des Linker auf den Zeitpunkt der Initialisierung zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b8304-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8304-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8304-114">Requirements</span></span>  
 <span data-ttu-id="b8304-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="b8304-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8304-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8304-116">See also</span></span>

- [<span data-ttu-id="b8304-117">IALink3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8304-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="b8304-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="b8304-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="b8304-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8304-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b8304-120">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="b8304-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
