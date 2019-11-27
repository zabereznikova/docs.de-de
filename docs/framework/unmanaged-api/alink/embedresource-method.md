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
ms.openlocfilehash: 24279870e7406de649df56e8aad31252513e95c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446539"
---
# <a name="embedresource-method"></a><span data-ttu-id="d544d-102">EmbedResource-Methode</span><span class="sxs-lookup"><span data-stu-id="d544d-102">EmbedResource Method</span></span>
<span data-ttu-id="d544d-103">Deklariert eine eingebettete Ressource.</span><span class="sxs-lookup"><span data-stu-id="d544d-103">Declares an embedded resource.</span></span> <span data-ttu-id="d544d-104">Diese Methode bettet die Ressource nicht ein.</span><span class="sxs-lookup"><span data-stu-id="d544d-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d544d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d544d-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d544d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d544d-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d544d-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d544d-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d544d-108">Dateitoken oder Assembly-ID der Datei, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="d544d-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="d544d-109">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="d544d-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="d544d-110">Offset der Ressource von RVA.</span><span class="sxs-lookup"><span data-stu-id="d544d-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d544d-111">Barrierefreiheits Flags wie `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="d544d-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="d544d-112">Diese Flags können an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="d544d-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d544d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d544d-113">Return Value</span></span>  
 <span data-ttu-id="d544d-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d544d-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d544d-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d544d-115">Requirements</span></span>  
 <span data-ttu-id="d544d-116">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="d544d-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d544d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d544d-117">See also</span></span>

- [<span data-ttu-id="d544d-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d544d-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d544d-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d544d-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d544d-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="d544d-120">ALink API</span></span>](index.md)
