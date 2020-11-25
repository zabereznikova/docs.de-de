---
title: IMetaDataConverter::GetTypeLibFromMetaData-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: eed8661f8885ca16492ab336a599b5290057843a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714600"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="381a3-102">IMetaDataConverter::GetTypeLibFromMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="381a3-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>

<span data-ttu-id="381a3-103">Ruft einen Zeiger auf eine- `ITypeLib` Instanz ab, die die Typbibliothek mit den angegebenen Bibliotheks-und Modulnamen darstellt.</span><span class="sxs-lookup"><span data-stu-id="381a3-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="381a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="381a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="381a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="381a3-105">Parameters</span></span>  

 `strModule`  
 <span data-ttu-id="381a3-106">in Der Name des Moduls der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="381a3-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="381a3-107">in Der Name der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="381a3-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="381a3-108">vorgenommen Ein Zeiger auf einen Speicherort, der die Adresse der- `ITypeLib` Instanz empfängt, die die Typbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="381a3-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="381a3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="381a3-109">Requirements</span></span>  

 <span data-ttu-id="381a3-110">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="381a3-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="381a3-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="381a3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="381a3-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="381a3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="381a3-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="381a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381a3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="381a3-114">See also</span></span>

- [<span data-ttu-id="381a3-115">IMetaDataConverter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="381a3-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)
