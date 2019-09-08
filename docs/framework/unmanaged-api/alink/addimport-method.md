---
title: AddImport-Methode
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787667"
---
# <a name="addimport-method"></a><span data-ttu-id="bb9e4-102">AddImport-Methode</span><span class="sxs-lookup"><span data-stu-id="bb9e4-102">AddImport Method</span></span>
<span data-ttu-id="bb9e4-103">Fügt der Assembly Importe hinzu.</span><span class="sxs-lookup"><span data-stu-id="bb9e4-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb9e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb9e4-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb9e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb9e4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bb9e4-106">Eindeutige ID der Assembly, die erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb9e4-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="bb9e4-107">Die eindeutige ID, die von der [ImportFile-Methode](importfile-method.md)abgerufen wird, der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="bb9e4-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bb9e4-108">Com+ `ffContainsNoMetaData` -FileDef-Flags, `ffWriteable`z. b. und.</span><span class="sxs-lookup"><span data-stu-id="bb9e4-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="bb9e4-109">`dwFlags`wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="bb9e4-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="bb9e4-110">Zeiger auf das Token, das die ID für die resultierende Datei empfängt.</span><span class="sxs-lookup"><span data-stu-id="bb9e4-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb9e4-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb9e4-111">Return Value</span></span>  
 <span data-ttu-id="bb9e4-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="bb9e4-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb9e4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb9e4-113">Requirements</span></span>  
 <span data-ttu-id="bb9e4-114">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="bb9e4-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9e4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb9e4-115">See also</span></span>

- [<span data-ttu-id="bb9e4-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb9e4-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bb9e4-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb9e4-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bb9e4-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="bb9e4-118">ALink API</span></span>](index.md)
