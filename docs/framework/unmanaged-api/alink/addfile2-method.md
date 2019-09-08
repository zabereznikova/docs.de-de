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
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777522"
---
# <a name="addfile2-method"></a><span data-ttu-id="3c538-102">AddFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="3c538-102">AddFile2 Method</span></span>
<span data-ttu-id="3c538-103">Fügt der Assembly Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c538-103">Adds files to the assembly.</span></span> <span data-ttu-id="3c538-104">Kann auch verwendet werden, um ungebundene Module zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c538-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c538-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c538-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c538-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c538-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3c538-107">ID für die Assembly, der die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3c538-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="3c538-108">Der Name der hinzu zufügenden Datei.</span><span class="sxs-lookup"><span data-stu-id="3c538-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3c538-109">Com+ `FileDef` `ffContainsNoMetaData` -Flags, wie `ffWriteable`z. b. und.</span><span class="sxs-lookup"><span data-stu-id="3c538-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="3c538-110">`dwFlags`wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="3c538-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="3c538-111">Schnittstelle zur [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3c538-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="3c538-112">Empfängt die ID für die Datei, die hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3c538-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c538-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3c538-113">Return Value</span></span>  
 <span data-ttu-id="3c538-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3c538-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c538-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c538-115">Requirements</span></span>  
 <span data-ttu-id="3c538-116">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="3c538-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c538-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c538-117">See also</span></span>

- [<span data-ttu-id="3c538-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c538-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3c538-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c538-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3c538-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="3c538-120">ALink API</span></span>](index.md)
