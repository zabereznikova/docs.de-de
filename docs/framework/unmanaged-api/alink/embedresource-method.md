---
title: EmbedResource-Methode
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: 34439b7c01dee7d7789d989b58e8944c6282b71b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676386"
---
# <a name="embedresource-method"></a><span data-ttu-id="2d49e-102">EmbedResource-Methode</span><span class="sxs-lookup"><span data-stu-id="2d49e-102">EmbedResource Method</span></span>

<span data-ttu-id="2d49e-103">Deklariert eine eingebettete Ressource.</span><span class="sxs-lookup"><span data-stu-id="2d49e-103">Declares an embedded resource.</span></span> <span data-ttu-id="2d49e-104">Diese Methode bettet die Ressource nicht ein.</span><span class="sxs-lookup"><span data-stu-id="2d49e-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d49e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d49e-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d49e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d49e-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="2d49e-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="2d49e-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2d49e-108">Dateitoken oder Assembly-ID der Datei, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="2d49e-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="2d49e-109">Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="2d49e-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="2d49e-110">Offset der Ressource von RVA.</span><span class="sxs-lookup"><span data-stu-id="2d49e-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2d49e-111">Barrierefreiheits Flags wie `mrPublic` und `mrPrivate` .</span><span class="sxs-lookup"><span data-stu-id="2d49e-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="2d49e-112">Diese Flags können an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="2d49e-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d49e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d49e-113">Return Value</span></span>  

 <span data-ttu-id="2d49e-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2d49e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d49e-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d49e-115">Requirements</span></span>  

 <span data-ttu-id="2d49e-116">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="2d49e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d49e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d49e-117">See also</span></span>

- [<span data-ttu-id="2d49e-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d49e-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2d49e-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d49e-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2d49e-120">ALink-API</span><span class="sxs-lookup"><span data-stu-id="2d49e-120">ALink API</span></span>](index.md)
