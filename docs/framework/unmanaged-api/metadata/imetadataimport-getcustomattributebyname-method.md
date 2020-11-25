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
ms.openlocfilehash: 3eb894aaf8ccdc99ea23ddf946f39f3ec71773d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711207"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="f8529-102">IMetaDataImport::GetCustomAttributeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="f8529-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>

<span data-ttu-id="f8529-103">Ruft das benutzerdefinierte Attribut ab, wenn Name und Besitzer angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="f8529-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8529-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8529-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8529-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8529-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="f8529-106">in Ein Metadatentoken, das das Objekt darstellt, das das benutzerdefinierte Attribut besitzt.</span><span class="sxs-lookup"><span data-stu-id="f8529-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="f8529-107">in Der Name des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="f8529-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="f8529-108">vorgenommen Ein Zeiger auf ein Array von Daten, das den Wert des benutzerdefinierten Attributs ist.</span><span class="sxs-lookup"><span data-stu-id="f8529-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="f8529-109">vorgenommen Die Größe der Daten in Bytes, die in \* zurückgegeben werden `ppData` .</span><span class="sxs-lookup"><span data-stu-id="f8529-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8529-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8529-110">Remarks</span></span>  

 <span data-ttu-id="f8529-111">Es ist zulässig, mehrere benutzerdefinierte Attribute für denselben Besitzer zu definieren. Sie haben möglicherweise sogar denselben Namen.</span><span class="sxs-lookup"><span data-stu-id="f8529-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="f8529-112">Es wird jedoch `GetCustomAttributeByName` nur eine Instanz von zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f8529-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="f8529-113">( `GetCustomAttributeByName` gibt die erste Instanz zurück, die erkannt wird.) Um alle Instanzen eines benutzerdefinierten Attributs zu suchen, müssen Sie die [IMetaDataImport:: enumcustomtribute](imetadataimport-enumcustomattributes-method.md) -Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f8529-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8529-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f8529-114">Requirements</span></span>  

 <span data-ttu-id="f8529-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8529-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8529-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f8529-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8529-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f8529-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8529-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8529-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8529-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8529-119">See also</span></span>

- [<span data-ttu-id="f8529-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8529-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f8529-121">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8529-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
