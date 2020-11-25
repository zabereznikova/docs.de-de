---
title: IMetaDataImport::GetNestedClassProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
ms.openlocfilehash: 8c0496c34c43a71ec4f51ba66b3bb18790023a2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722296"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="e73a6-102">IMetaDataImport::GetNestedClassProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e73a6-102">IMetaDataImport::GetNestedClassProps Method</span></span>

<span data-ttu-id="e73a6-103">Ruft das TypeDef-Token für das <xref:System.Type> übergeordnete Element des angegebenen eingefügten Typs ab.</span><span class="sxs-lookup"><span data-stu-id="e73a6-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e73a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e73a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e73a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e73a6-105">Parameters</span></span>  

 `tdNestedClass`  
 <span data-ttu-id="e73a6-106">in Ein TypeDef-Token, das den darstellt <xref:System.Type> , für den das übergeordnete Klassen Token zurückgegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="e73a6-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="e73a6-107">vorgenommen Ein Zeiger auf das TypeDef-Token für das <xref:System.Type> , das `tdNestedClass` in eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="e73a6-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e73a6-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e73a6-108">Requirements</span></span>  

 <span data-ttu-id="e73a6-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e73a6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e73a6-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e73a6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e73a6-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e73a6-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e73a6-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e73a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73a6-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e73a6-113">See also</span></span>

- [<span data-ttu-id="e73a6-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e73a6-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e73a6-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e73a6-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
