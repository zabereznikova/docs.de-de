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
ms.openlocfilehash: b771b368c069a4577d266b47bfb4a5ee1935e48e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436273"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="d7e4d-102">IMetaDataConverter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7e4d-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="d7e4d-103">Stellt Methoden zum Zuordnen von Typbibliotheken zu ihren Metadatensignaturen sowie zum gegenseitigen Konvertieren bereit.</span><span class="sxs-lookup"><span data-stu-id="d7e4d-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7e4d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d7e4d-104">Methods</span></span>  
  
|<span data-ttu-id="d7e4d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d7e4d-105">Method</span></span>|<span data-ttu-id="d7e4d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7e4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7e4d-107">GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="d7e4d-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="d7e4d-108">Ruft einen Zeiger auf eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Instanz ab, die die Metadatensignatur für die Typbibliothek darstellt, auf die von der angegebenen `ITypeInfo`-Instanz verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d7e4d-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="d7e4d-109">GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="d7e4d-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="d7e4d-110">Ruft einen Zeiger auf eine `IMetaDataImport`-Instanz ab, die die Metadatensignatur für die Typbibliothek darstellt, die durch die angegebene `ITypeLib` Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d7e4d-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="d7e4d-111">GetTypeLibFromMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="d7e4d-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="d7e4d-112">Ruft einen Zeiger auf eine `ITypeLib`-Instanz ab, die die Typbibliothek mit den angegebenen Modul-und Bibliotheksnamen darstellt.</span><span class="sxs-lookup"><span data-stu-id="d7e4d-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7e4d-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d7e4d-113">Requirements</span></span>  
 <span data-ttu-id="d7e4d-114">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7e4d-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e4d-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d7e4d-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7e4d-116">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7e4d-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7e4d-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e4d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e4d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7e4d-118">See also</span></span>

- [<span data-ttu-id="d7e4d-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d7e4d-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="d7e4d-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7e4d-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
