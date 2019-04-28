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
ms.openlocfilehash: 7a651be40773607e0db215eadf884ed642e6e3b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775667"
---
# <a name="addfile2-method"></a><span data-ttu-id="b3478-102">AddFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="b3478-102">AddFile2 Method</span></span>
<span data-ttu-id="b3478-103">Dateien hinzugefügt der Assembly.</span><span class="sxs-lookup"><span data-stu-id="b3478-103">Adds files to the assembly.</span></span> <span data-ttu-id="b3478-104">Kann auch zum Erstellen von ungebundener Modules verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3478-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3478-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3478-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3478-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3478-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b3478-107">Die ID für die Assembly, die die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b3478-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="b3478-108">Der Name der Datei, die hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b3478-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b3478-109">COM+ `FileDef` flags, z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="b3478-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="b3478-110">`dwFlags` wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="b3478-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="b3478-111">Schnittstelle zum [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b3478-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="b3478-112">Empfängt die ID für die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b3478-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3478-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b3478-113">Return Value</span></span>  
 <span data-ttu-id="b3478-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b3478-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3478-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3478-115">Requirements</span></span>  
 <span data-ttu-id="b3478-116">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="b3478-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3478-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3478-117">See also</span></span>

- [<span data-ttu-id="b3478-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3478-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b3478-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3478-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b3478-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="b3478-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
