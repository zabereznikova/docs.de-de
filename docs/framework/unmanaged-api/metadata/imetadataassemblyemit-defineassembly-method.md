---
title: IMetaDataAssemblyEmit::DefineAssembly-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 6d783e27c60db7381025f3b2382728e3996323ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725728"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="d4fb4-102">IMetaDataAssemblyEmit::DefineAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="d4fb4-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>

<span data-ttu-id="d4fb4-103">Erstellt eine `Assembly` -Struktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4fb4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4fb4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4fb4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4fb4-105">Parameters</span></span>  

 `pbPublicKey`  
 <span data-ttu-id="d4fb4-106">in Der öffentliche Schlüssel, der den Verleger der Assembly identifiziert, oder NULL, wenn die Assembly nicht den starken Namen hat.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="d4fb4-107">in Die Größe von in Bytes `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="d4fb4-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="d4fb4-108">in Der Bezeichner des Hash Algorithmus, der zum Verschlüsseln der Dateien in der Assembly verwendet werden soll, oder NULL, um den SHA-1-Algorithmus anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="d4fb4-109">in Der lesbare Textname der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="d4fb4-110">Dieser Wert darf nicht länger als 1024 Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d4fb4-111">in Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Versions-, Platt Form-und Gebiets Schema Informationen für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="d4fb4-112">in Eine Kombination aus [CorAssemblyFlags](corassemblyflags-enumeration.md) -Werten, mit denen die Funktionen der Assembly beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-112">[in] A combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="d4fb4-113">vorgenommen Ein Zeiger auf das Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4fb4-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4fb4-114">Remarks</span></span>  

 <span data-ttu-id="d4fb4-115">`Assembly`In einem Manifest kann nur eine Metadatenstruktur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4fb4-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4fb4-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d4fb4-116">Requirements</span></span>  

 <span data-ttu-id="d4fb4-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4fb4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4fb4-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d4fb4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4fb4-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d4fb4-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4fb4-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4fb4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fb4-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4fb4-121">See also</span></span>

- [<span data-ttu-id="d4fb4-122">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4fb4-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
