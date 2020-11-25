---
title: IMetaDataImport::IsGlobal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
ms.openlocfilehash: 0d76abf8a9c923089f367ab4e1786ac8cc92622d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702978"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="920e8-102">IMetaDataImport::IsGlobal-Methode</span><span class="sxs-lookup"><span data-stu-id="920e8-102">IMetaDataImport::IsGlobal Method</span></span>

<span data-ttu-id="920e8-103">Ruft einen Wert ab, der angibt, ob für das durch das angegebene Metadatentoken dargestellte Feld, die Methode oder den Typ der globale Bereich gilt.</span><span class="sxs-lookup"><span data-stu-id="920e8-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="920e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="920e8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="920e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="920e8-105">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="920e8-106">in Ein Metadatentoken, das einen Typ, ein Feld oder eine Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="920e8-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="920e8-107">[out] 1, wenn das Objekt über einen globalen Gültigkeitsbereich verfügt. andernfalls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="920e8-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="920e8-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="920e8-108">Requirements</span></span>  

 <span data-ttu-id="920e8-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="920e8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="920e8-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="920e8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="920e8-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="920e8-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="920e8-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="920e8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920e8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="920e8-113">See also</span></span>

- [<span data-ttu-id="920e8-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="920e8-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="920e8-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="920e8-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
