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
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446683"
---
# <a name="addfile-method"></a><span data-ttu-id="c226e-102">AddFile-Methode</span><span class="sxs-lookup"><span data-stu-id="c226e-102">AddFile Method</span></span>
<span data-ttu-id="c226e-103">Fügt der Assembly Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="c226e-103">Adds files to the assembly.</span></span> <span data-ttu-id="c226e-104">Kann auch verwendet werden, um ungebundene Module zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c226e-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c226e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c226e-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c226e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c226e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c226e-107">Eindeutige ID der Assembly, die erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c226e-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="c226e-108">Der voll qualifizierte Name der hinzu zufügenden Datei.</span><span class="sxs-lookup"><span data-stu-id="c226e-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c226e-109">Com+-FileDef-Flags wie `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="c226e-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="c226e-110">`dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="c226e-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="c226e-111">[IMetaDataEmit-Schnittstellen](../metadata/imetadataemit-interface.md) Schnittstelle, die zum Ausgeben von Metadaten verwendet werden soll, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c226e-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="c226e-112">Ein Zeiger auf den Speicherort, an dem die eindeutige ID der hinzugefügten Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c226e-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c226e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c226e-113">Return Value</span></span>  
 <span data-ttu-id="c226e-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c226e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c226e-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c226e-115">Requirements</span></span>  
 <span data-ttu-id="c226e-116">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="c226e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c226e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c226e-117">See also</span></span>

- [<span data-ttu-id="c226e-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c226e-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c226e-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c226e-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c226e-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c226e-120">ALink API</span></span>](index.md)
