---
title: AddFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 53ca4005f5681cfc5d550301d8aad1406aceb3a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717200"
---
# <a name="addfile-method"></a><span data-ttu-id="de4e0-102">AddFile-Methode</span><span class="sxs-lookup"><span data-stu-id="de4e0-102">AddFile Method</span></span>

<span data-ttu-id="de4e0-103">Fügt der Assembly Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="de4e0-103">Adds files to the assembly.</span></span> <span data-ttu-id="de4e0-104">Kann auch verwendet werden, um ungebundene Module zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de4e0-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de4e0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="de4e0-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="de4e0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="de4e0-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="de4e0-107">Eindeutige ID der Assembly, die erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="de4e0-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="de4e0-108">Der voll qualifizierte Name der hinzu zufügenden Datei.</span><span class="sxs-lookup"><span data-stu-id="de4e0-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="de4e0-109">Com+-FileDef-Flags, z `ffContainsNoMetaData` `ffWriteable` . b. und.</span><span class="sxs-lookup"><span data-stu-id="de4e0-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="de4e0-110">`dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="de4e0-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="de4e0-111">[IMetaDataEmit-Schnittstellen](../metadata/imetadataemit-interface.md) Schnittstelle, die zum Ausgeben von Metadaten verwendet werden soll, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="de4e0-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="de4e0-112">Ein Zeiger auf den Speicherort, an dem die eindeutige ID der hinzugefügten Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="de4e0-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de4e0-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de4e0-113">Return Value</span></span>  

 <span data-ttu-id="de4e0-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="de4e0-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de4e0-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="de4e0-115">Requirements</span></span>  

 <span data-ttu-id="de4e0-116">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="de4e0-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4e0-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de4e0-117">See also</span></span>

- [<span data-ttu-id="de4e0-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de4e0-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="de4e0-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de4e0-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="de4e0-120">ALink-API</span><span class="sxs-lookup"><span data-stu-id="de4e0-120">ALink API</span></span>](index.md)
