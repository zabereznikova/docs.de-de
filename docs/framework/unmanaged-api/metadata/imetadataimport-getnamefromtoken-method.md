---
title: IMetaDataImport::GetNameFromToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 867fb0ee4bc1a093eb7fd46e25497d585c4d9b6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727496"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="b5599-102">IMetaDataImport::GetNameFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b5599-102">IMetaDataImport::GetNameFromToken Method</span></span>

<span data-ttu-id="b5599-103">Ruft den UTF-8-Namen des Objekts ab, auf das vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b5599-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="b5599-104">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="b5599-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5599-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5599-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5599-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5599-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="b5599-107">in Das Token, das das Objekt darstellt, für das der Name zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5599-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="b5599-108">vorgenommen Ein Zeiger auf den UTF-8-Objektnamen im Heap.</span><span class="sxs-lookup"><span data-stu-id="b5599-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5599-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5599-109">Remarks</span></span>  

 <span data-ttu-id="b5599-110">`GetNameFromToken` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="b5599-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="b5599-111">Als Alternative können Sie eine-Methode aufzurufen, um die Eigenschaften des jeweiligen Typs des erforderlichen Tokens abzurufen, z `GetFieldProps` . b. für ein Feld oder `GetMethodProps` für eine Methode.</span><span class="sxs-lookup"><span data-stu-id="b5599-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5599-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b5599-112">Requirements</span></span>  

 <span data-ttu-id="b5599-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5599-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5599-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b5599-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5599-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b5599-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5599-116">**.NET Framework Versionen:** 1,0</span><span class="sxs-lookup"><span data-stu-id="b5599-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5599-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5599-117">See also</span></span>

- [<span data-ttu-id="b5599-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5599-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b5599-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5599-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
