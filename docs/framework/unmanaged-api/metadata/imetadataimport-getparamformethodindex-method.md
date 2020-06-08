---
title: IMetaDataImport::GetParamForMethodIndex-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
ms.openlocfilehash: 21a83e404405ca9cfe301b76cb1e1591d69e747c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491120"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="1983f-102">IMetaDataImport::GetParamForMethodIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="1983f-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="1983f-103">Ruft das Token ab, das einen angegebenen Parameter der Methode darstellt, die durch das angegebene MethodDef-Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1983f-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1983f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1983f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1983f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1983f-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="1983f-106">in Ein Token, das die Methode darstellt, für die das Parameter Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="1983f-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="1983f-107">in Die Ordinalposition in der Parameterliste, in der der angeforderte Parameter auftritt.</span><span class="sxs-lookup"><span data-stu-id="1983f-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="1983f-108">Parameter werden beginnend mit 1 nummeriert, wobei der Rückgabewert der Methode an Position 0 (null) liegt.</span><span class="sxs-lookup"><span data-stu-id="1983f-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="1983f-109">vorgenommen Ein Zeiger auf ein ParamDef-Token, das den angeforderten Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="1983f-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1983f-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1983f-110">Requirements</span></span>  
 <span data-ttu-id="1983f-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1983f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1983f-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1983f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1983f-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1983f-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1983f-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1983f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1983f-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="1983f-115">See also</span></span>

- [<span data-ttu-id="1983f-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1983f-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1983f-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1983f-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
