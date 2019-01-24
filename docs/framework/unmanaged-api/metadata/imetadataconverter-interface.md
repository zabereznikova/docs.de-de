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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc1f813cac237642fdaab653cd47552ab7472ab0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732925"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="6d431-102">IMetaDataConverter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d431-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="6d431-103">Stellt Methoden zum Zuordnen von Typbibliotheken zu ihren Metadatensignaturen sowie zum gegenseitigen Konvertieren bereit.</span><span class="sxs-lookup"><span data-stu-id="6d431-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d431-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6d431-104">Methods</span></span>  
  
|<span data-ttu-id="6d431-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6d431-105">Method</span></span>|<span data-ttu-id="6d431-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d431-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d431-107">GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="6d431-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="6d431-108">Ruft einen Zeiger auf ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Instanz, die die Signatur der Metadaten für die Typbibliothek, auf die verwiesen wird durch das angegebene darstellt `ITypeInfo` Instanz.</span><span class="sxs-lookup"><span data-stu-id="6d431-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="6d431-109">GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="6d431-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="6d431-110">Ruft einen Zeiger auf ein `IMetaDataImport` Instanz, die die Signatur der Metadaten für die Typbibliothek, dargestellt durch das angegebene darstellt `ITypeLib` Instanz.</span><span class="sxs-lookup"><span data-stu-id="6d431-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="6d431-111">GetTypeLibFromMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="6d431-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="6d431-112">Ruft einen Zeiger auf ein `ITypeLib` -Instanz, die die Typbibliothek darstellt, die die angegebenen Namen der Module und -Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="6d431-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d431-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d431-113">Requirements</span></span>  
 <span data-ttu-id="6d431-114">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d431-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d431-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d431-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d431-116">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6d431-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d431-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d431-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d431-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d431-118">See also</span></span>
- [<span data-ttu-id="6d431-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6d431-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="6d431-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d431-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
