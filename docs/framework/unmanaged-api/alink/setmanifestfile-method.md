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
ms.openlocfilehash: a4518e93db887dbdc4397636479be8bf5a705c2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733723"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="8ec15-102">SetManifestFile-Methode</span><span class="sxs-lookup"><span data-stu-id="8ec15-102">SetManifestFile Method</span></span>

<span data-ttu-id="8ec15-103">Ermöglicht es Ihnen, die Manifest-Datei anzugeben oder zurückzusetzen, die der Linker beim Erstellen der Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ec15-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ec15-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ec15-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ec15-105">Parameters</span></span>  

 `pszFile`  
  
 <span data-ttu-id="8ec15-106">Der Name der Manifest-Datei, deren Inhalt in das Win32-Ressourcen-BLOB eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8ec15-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ec15-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8ec15-107">Return Value</span></span>  

 <span data-ttu-id="8ec15-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="8ec15-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ec15-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ec15-109">Remarks</span></span>  

 <span data-ttu-id="8ec15-110">Nennen Sie dies, bevor Sie die Win32ResBlob anfordern.</span><span class="sxs-lookup"><span data-stu-id="8ec15-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="8ec15-111">Der Wert des- `pszFile` Parameters ist der Name der Manifest-Datei, deren Inhalt in den Win32-Ressourcen mit der ID RT_MANIFEST gelesen und abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8ec15-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="8ec15-112">Wenn Sie mit einem Parameter von NULL aufgerufen wird, werden alle zuvor gelesenen Manifeste gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8ec15-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="8ec15-113">Dadurch kann der Zustand des Linker auf den Zeitpunkt der Initialisierung zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="8ec15-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ec15-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8ec15-114">Requirements</span></span>  

 <span data-ttu-id="8ec15-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="8ec15-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec15-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ec15-116">See also</span></span>

- [<span data-ttu-id="8ec15-117">IALink3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ec15-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="8ec15-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="8ec15-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="8ec15-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ec15-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8ec15-120">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="8ec15-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
