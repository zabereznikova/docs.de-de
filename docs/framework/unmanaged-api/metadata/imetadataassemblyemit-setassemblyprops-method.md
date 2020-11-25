---
title: IMetaDataAssemblyEmit::SetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: 3736e7279056e015b157758b1233cf6dc5aa6d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720203"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="cd7cc-102">IMetaDataAssemblyEmit::SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="cd7cc-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>

<span data-ttu-id="cd7cc-103">Ändert die angegebene `Assembly`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd7cc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd7cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd7cc-105">Parameters</span></span>  

 `pma`  
 <span data-ttu-id="cd7cc-106">in Das Metadatentoken, das die `Assembly` zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="cd7cc-107">in Ein Zeiger auf den öffentlichen Schlüssel des Verlegers der Assembly.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="cd7cc-108">in Die Größe von in Bytes `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="cd7cc-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="cd7cc-109">in Der Bezeichner für den Hash Algorithmus, der zum Hash der Assemblydateien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="cd7cc-110">in Der lesbare Textname der Assembly.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="cd7cc-111">in Ein Zeiger auf die ASSEMBLYMETADATA, die Informationen zu Version, Plattform und Gebiets Schema für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="cd7cc-112">in Eine bitweise Kombination von [AssemblyFlags](assemblyflags-enumeration.md) -Werten, die verschiedene Attribute der Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-112">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd7cc-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd7cc-113">Remarks</span></span>  

 <span data-ttu-id="cd7cc-114">Verwenden Sie zum Erstellen einer `Assembly` Metadatenstruktur die [IMetaDataAssemblyEmit::D efineassembly](imetadataassemblyemit-defineassembly-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd7cc-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cd7cc-115">Requirements</span></span>  

 <span data-ttu-id="cd7cc-116">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd7cc-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd7cc-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cd7cc-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd7cc-118">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd7cc-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd7cc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7cc-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd7cc-120">See also</span></span>

- [<span data-ttu-id="cd7cc-121">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd7cc-121">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
