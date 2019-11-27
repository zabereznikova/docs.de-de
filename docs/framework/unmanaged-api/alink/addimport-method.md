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
ms.openlocfilehash: 52e52ac62e2dcfeb182da3014a863409f640274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446657"
---
# <a name="addimport-method"></a><span data-ttu-id="f3e10-102">AddImport-Methode</span><span class="sxs-lookup"><span data-stu-id="f3e10-102">AddImport Method</span></span>
<span data-ttu-id="f3e10-103">Fügt der Assembly Importe hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3e10-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3e10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3e10-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3e10-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3e10-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f3e10-106">Eindeutige ID der Assembly, die erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3e10-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="f3e10-107">Die eindeutige ID, die von der [ImportFile-Methode](importfile-method.md)abgerufen wird, der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="f3e10-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f3e10-108">Com+-FileDef-Flags wie `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="f3e10-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="f3e10-109">`dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="f3e10-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="f3e10-110">Zeiger auf das Token, das die ID für die resultierende Datei empfängt.</span><span class="sxs-lookup"><span data-stu-id="f3e10-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3e10-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3e10-111">Return Value</span></span>  
 <span data-ttu-id="f3e10-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f3e10-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3e10-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f3e10-113">Requirements</span></span>  
 <span data-ttu-id="f3e10-114">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="f3e10-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e10-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3e10-115">See also</span></span>

- [<span data-ttu-id="f3e10-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3e10-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f3e10-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3e10-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f3e10-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="f3e10-118">ALink API</span></span>](index.md)
