---
title: IMetaDataImport::GetCustomAttributeByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: bd7ba7ff10918e5953ea8ae89a60af3115af48a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437680"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="c6dc2-102">IMetaDataImport::GetCustomAttributeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="c6dc2-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="c6dc2-103">Ruft das benutzerdefinierte Attribut ab, wenn Name und Besitzer angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6dc2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6dc2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6dc2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6dc2-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="c6dc2-106">in Ein Metadatentoken, das das Objekt darstellt, das das benutzerdefinierte Attribut besitzt.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="c6dc2-107">in Der Name des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="c6dc2-108">vorgenommen Ein Zeiger auf ein Array von Daten, das den Wert des benutzerdefinierten Attributs ist.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="c6dc2-109">vorgenommen Die Größe der Daten in Bytes, die in \*`ppData`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6dc2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6dc2-110">Remarks</span></span>  
 <span data-ttu-id="c6dc2-111">Es ist zulässig, mehrere benutzerdefinierte Attribute für denselben Besitzer zu definieren. Sie haben möglicherweise sogar denselben Namen.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="c6dc2-112">`GetCustomAttributeByName` gibt jedoch nur eine Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="c6dc2-113">(`GetCustomAttributeByName` gibt die erste Instanz zurück, die erkannt wird.) Um alle Instanzen eines benutzerdefinierten Attributs zu suchen, müssen Sie die [IMetaDataImport:: enumcustomtribute](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) -Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c6dc2-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6dc2-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c6dc2-114">Requirements</span></span>  
 <span data-ttu-id="c6dc2-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6dc2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6dc2-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c6dc2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6dc2-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c6dc2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6dc2-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6dc2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6dc2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6dc2-119">See also</span></span>

- [<span data-ttu-id="c6dc2-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6dc2-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c6dc2-121">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6dc2-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
