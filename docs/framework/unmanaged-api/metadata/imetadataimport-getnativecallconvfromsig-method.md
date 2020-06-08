---
title: IMetaDataImport::GetNativeCallConvFromSig-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
ms.openlocfilehash: 44439eda62f85c32893b73f17bd057195cf6b2e1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503548"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="65ec3-102">IMetaDataImport::GetNativeCallConvFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="65ec3-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="65ec3-103">Ruft die systemeigene Aufrufkonvention für die Methode ab, die durch den angegebenen Signaturzeiger dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="65ec3-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65ec3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65ec3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65ec3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65ec3-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="65ec3-106">in Ein Zeiger auf die Metadatensignatur der Methode, für die die Aufruf Konvention zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="65ec3-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="65ec3-107">in Die Größe von in Bytes `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="65ec3-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="65ec3-108">vorgenommen Ein Zeiger auf die systemeigene Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="65ec3-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65ec3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="65ec3-109">Requirements</span></span>  
 <span data-ttu-id="65ec3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65ec3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65ec3-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="65ec3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65ec3-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="65ec3-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65ec3-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65ec3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ec3-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="65ec3-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="65ec3-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65ec3-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="65ec3-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65ec3-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
