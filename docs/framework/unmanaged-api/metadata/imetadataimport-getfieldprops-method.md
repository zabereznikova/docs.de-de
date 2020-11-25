---
title: IMetaDataImport::GetFieldProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
ms.openlocfilehash: 458a90bc47711d9f831805faa8468a49f3e0d305
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703996"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="bffc0-102">IMetaDataImport::GetFieldProps-Methode</span><span class="sxs-lookup"><span data-stu-id="bffc0-102">IMetaDataImport::GetFieldProps Method</span></span>

<span data-ttu-id="bffc0-103">Ruft Metadaten ab, die dem Feld zugeordnet sind, auf das durch das angegebene FieldDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bffc0-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bffc0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bffc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bffc0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bffc0-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="bffc0-106">in Ein FieldDef-Token, das das Feld darstellt, für das zugeordnete Metadaten zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="bffc0-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="bffc0-107">vorgenommen Ein Zeiger auf ein TypeDef-Token, das den Typ der Klasse darstellt, zu der das Feld gehört.</span><span class="sxs-lookup"><span data-stu-id="bffc0-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="bffc0-108">vorgenommen Der Name des Felds.</span><span class="sxs-lookup"><span data-stu-id="bffc0-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="bffc0-109">in Die Größe des Puffers für *szField* in breit Zeichen.</span><span class="sxs-lookup"><span data-stu-id="bffc0-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="bffc0-110">vorgenommen Die tatsächliche Größe des zurückgegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="bffc0-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="bffc0-111">vorgenommen Flags, die den Metadaten des Felds zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bffc0-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="bffc0-112">in Ein Zeiger auf den binären Metadatenwert, der das Feld beschreibt.</span><span class="sxs-lookup"><span data-stu-id="bffc0-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="bffc0-113">vorgenommen Die Größe von in Bytes `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="bffc0-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="bffc0-114">vorgenommen Ein Flag, das den Werttyp des Felds angibt.</span><span class="sxs-lookup"><span data-stu-id="bffc0-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="bffc0-115">vorgenommen Ein konstanter Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="bffc0-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="bffc0-116">vorgenommen Die Größe in Zeichen von `ppValue` , oder 0 (null), wenn keine Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bffc0-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bffc0-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bffc0-117">Requirements</span></span>  

 <span data-ttu-id="bffc0-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bffc0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bffc0-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bffc0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bffc0-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bffc0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bffc0-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bffc0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bffc0-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bffc0-122">See also</span></span>

- [<span data-ttu-id="bffc0-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bffc0-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="bffc0-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bffc0-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
