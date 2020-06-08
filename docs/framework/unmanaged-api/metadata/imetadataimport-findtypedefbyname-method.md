---
title: IMetaDataImport::FindTypeDefByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
ms.openlocfilehash: 5485f43afe08fafa559d0418327a8f4f186860e7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491510"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="df435-102">IMetaDataImport::FindTypeDefByName-Methode</span><span class="sxs-lookup"><span data-stu-id="df435-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="df435-103">Ruft einen Zeiger auf das TypeDef-Metadatentoken für <xref:System.Type> mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="df435-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df435-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df435-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df435-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df435-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="df435-106">in Der Name des Typs, für den das TypeDef-Token angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="df435-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="df435-107">in Ein TypeDef-oder TypeRef-Token, das die einschließende Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="df435-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="df435-108">Wenn der zu suchende Typ keine Unterklasse ist, legen Sie diesen Wert auf NULL fest.</span><span class="sxs-lookup"><span data-stu-id="df435-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="df435-109">vorgenommen Ein Zeiger auf das übereinstimmende TypeDef-Token.</span><span class="sxs-lookup"><span data-stu-id="df435-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df435-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df435-110">Requirements</span></span>  
 <span data-ttu-id="df435-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df435-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df435-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="df435-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df435-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="df435-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df435-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df435-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df435-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="df435-115">See also</span></span>

- [<span data-ttu-id="df435-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df435-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="df435-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df435-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
