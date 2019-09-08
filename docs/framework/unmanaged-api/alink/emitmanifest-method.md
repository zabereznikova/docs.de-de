---
title: EmitManifest-Methode
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdab1fd10be8fd245f4348798232964721b4487a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777339"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="fa21b-102">EmitManifest-Methode</span><span class="sxs-lookup"><span data-stu-id="fa21b-102">EmitManifest Method</span></span>
<span data-ttu-id="fa21b-103">Gibt das endgültige Manifest aus.</span><span class="sxs-lookup"><span data-stu-id="fa21b-103">Emits the final manifest.</span></span> <span data-ttu-id="fa21b-104">Ruft diese Methode auf, nachdem alle anderen Dateien importiert und alle Optionen festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="fa21b-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="fa21b-105">Diese Methode darf nicht für ungebundene Module aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fa21b-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa21b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa21b-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa21b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa21b-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fa21b-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="fa21b-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="fa21b-109">Empfängt die von der [StrongNameSignatureSize-Funktion](../strong-naming/strongnamesignaturesize-function.md)abgerufene Größe in der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="fa21b-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="fa21b-110">Empfängt optional das assemblymanifestoken.</span><span class="sxs-lookup"><span data-stu-id="fa21b-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa21b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa21b-111">Return Value</span></span>  
 <span data-ttu-id="fa21b-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="fa21b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa21b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa21b-113">Requirements</span></span>  
 <span data-ttu-id="fa21b-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="fa21b-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa21b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa21b-115">See also</span></span>

- [<span data-ttu-id="fa21b-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa21b-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fa21b-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa21b-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fa21b-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="fa21b-118">ALink API</span></span>](index.md)
