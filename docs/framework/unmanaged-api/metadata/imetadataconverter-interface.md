---
title: IMetaDataConverter-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b6ca7c619d32e69ffac20b80561171d0320db2d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008377"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="dff83-102">IMetaDataConverter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dff83-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="dff83-103">Stellt Methoden zum Zuordnen von Typbibliotheken zu ihren Metadatensignaturen sowie zum gegenseitigen Konvertieren bereit.</span><span class="sxs-lookup"><span data-stu-id="dff83-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dff83-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="dff83-104">Methods</span></span>  
  
|<span data-ttu-id="dff83-105">Methode</span><span class="sxs-lookup"><span data-stu-id="dff83-105">Method</span></span>|<span data-ttu-id="dff83-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dff83-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dff83-107">GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="dff83-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="dff83-108">Ruft einen Zeiger auf eine [IMetaDataImport](imetadataimport-interface.md) -Instanz ab, die die Metadatensignatur der Typbibliothek darstellt, auf die von der angegebenen-Instanz verwiesen wird `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="dff83-108">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="dff83-109">GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="dff83-109">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="dff83-110">Ruft einen Zeiger auf eine- `IMetaDataImport` Instanz ab, die die Metadatensignatur für die Typbibliothek darstellt, die von der angegebenen-Instanz dargestellt wird `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="dff83-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="dff83-111">GetTypeLibFromMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="dff83-111">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="dff83-112">Ruft einen Zeiger auf eine- `ITypeLib` Instanz ab, die die Typbibliothek darstellt, die über die angegebenen Module und Bibliotheksnamen verfügt.</span><span class="sxs-lookup"><span data-stu-id="dff83-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dff83-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dff83-113">Requirements</span></span>  
 <span data-ttu-id="dff83-114">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dff83-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff83-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dff83-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dff83-116">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="dff83-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dff83-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff83-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff83-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dff83-118">See also</span></span>

- [<span data-ttu-id="dff83-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="dff83-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="dff83-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dff83-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
