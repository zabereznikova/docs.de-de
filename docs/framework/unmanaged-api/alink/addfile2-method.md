---
title: AddFile2-Methode
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4735103f277d710dd23adfa19c475c425feaa36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403330"
---
# <a name="addfile2-method"></a><span data-ttu-id="c8033-102">AddFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="c8033-102">AddFile2 Method</span></span>
<span data-ttu-id="c8033-103">Dateien hinzugefügt der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c8033-103">Adds files to the assembly.</span></span> <span data-ttu-id="c8033-104">Kann auch zum Erstellen von ungebundener Modules verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8033-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8033-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8033-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8033-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8033-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c8033-107">Die ID für die Assembly, die die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c8033-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="c8033-108">Der Name der Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c8033-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c8033-109">COM+- `FileDef` kennzeichnet, wie z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="c8033-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="c8033-110">`dwFlags` wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="c8033-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="c8033-111">Schnittstelle zu [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c8033-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="c8033-112">Empfängt die ID für die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c8033-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8033-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8033-113">Return Value</span></span>  
 <span data-ttu-id="c8033-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8033-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8033-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8033-115">Requirements</span></span>  
 <span data-ttu-id="c8033-116">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="c8033-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8033-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8033-117">See Also</span></span>  
 [<span data-ttu-id="c8033-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8033-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c8033-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8033-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c8033-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c8033-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
